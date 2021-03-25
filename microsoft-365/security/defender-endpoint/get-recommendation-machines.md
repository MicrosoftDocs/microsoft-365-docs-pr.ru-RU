---
title: Список устройств по рекомендации
description: Извлекает список устройств, связанных с рекомендацией по безопасности.
keywords: apis, graph api, supported apis, get, security recommendation for vulnerable devices, threat and vulnerability management, threat and vulnerability management api
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
ms.openlocfilehash: 515542f6eca208e92228a8d0b344b6013b11a148
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198274"
---
# <a name="list-devices-by-recommendation"></a><span data-ttu-id="84ed5-104">Список устройств по рекомендации</span><span class="sxs-lookup"><span data-stu-id="84ed5-104">List devices by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="84ed5-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="84ed5-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="84ed5-106">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="84ed5-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="84ed5-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="84ed5-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="84ed5-108">Извлекает список устройств, связанных с рекомендацией по безопасности.</span><span class="sxs-lookup"><span data-stu-id="84ed5-108">Retrieves a list of devices associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="84ed5-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="84ed5-109">Permissions</span></span>
<span data-ttu-id="84ed5-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="84ed5-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="84ed5-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="84ed5-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="84ed5-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="84ed5-112">Permission type</span></span> |   <span data-ttu-id="84ed5-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="84ed5-113">Permission</span></span>  |   <span data-ttu-id="84ed5-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="84ed5-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="84ed5-115">Application</span><span class="sxs-lookup"><span data-stu-id="84ed5-115">Application</span></span> |   <span data-ttu-id="84ed5-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="84ed5-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="84ed5-117">'Read Threat and Vulnerability Management security recommendation information'</span><span class="sxs-lookup"><span data-stu-id="84ed5-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="84ed5-118">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="84ed5-118">Delegated (work or school account)</span></span> | <span data-ttu-id="84ed5-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="84ed5-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="84ed5-120">'Read Threat and Vulnerability Management security recommendation information'</span><span class="sxs-lookup"><span data-stu-id="84ed5-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="84ed5-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="84ed5-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/machineReferences
```

## <a name="request-headers"></a><span data-ttu-id="84ed5-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="84ed5-122">Request headers</span></span>

<span data-ttu-id="84ed5-123">Имя</span><span class="sxs-lookup"><span data-stu-id="84ed5-123">Name</span></span> | <span data-ttu-id="84ed5-124">Тип</span><span class="sxs-lookup"><span data-stu-id="84ed5-124">Type</span></span> | <span data-ttu-id="84ed5-125">Описание</span><span class="sxs-lookup"><span data-stu-id="84ed5-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="84ed5-126">Авторизация</span><span class="sxs-lookup"><span data-stu-id="84ed5-126">Authorization</span></span> | <span data-ttu-id="84ed5-127">Строка</span><span class="sxs-lookup"><span data-stu-id="84ed5-127">String</span></span> | <span data-ttu-id="84ed5-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="84ed5-128">Bearer {token}.</span></span> <span data-ttu-id="84ed5-129">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="84ed5-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="84ed5-130">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="84ed5-130">Request body</span></span>
<span data-ttu-id="84ed5-131">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="84ed5-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="84ed5-132">Отклик</span><span class="sxs-lookup"><span data-stu-id="84ed5-132">Response</span></span>
<span data-ttu-id="84ed5-133">В случае успеха этот метод возвращает 200 ОК со списком устройств, связанных с рекомендацией по безопасности.</span><span class="sxs-lookup"><span data-stu-id="84ed5-133">If successful, this method returns 200 OK with the list of devices associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="84ed5-134">Пример</span><span class="sxs-lookup"><span data-stu-id="84ed5-134">Example</span></span>

<span data-ttu-id="84ed5-135">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="84ed5-135">**Request**</span></span>

<span data-ttu-id="84ed5-136">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="84ed5-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/machineReferences
```

<span data-ttu-id="84ed5-137">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="84ed5-137">**Response**</span></span>

<span data-ttu-id="84ed5-138">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="84ed5-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "e058770379bc199a9c179ce52a23e16fd44fd2ee",
            "computerDnsName": "niw_pc",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="84ed5-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="84ed5-139">Related topics</span></span>
- [<span data-ttu-id="84ed5-140">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="84ed5-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="84ed5-141">Рекомендация по & уязвимости</span><span class="sxs-lookup"><span data-stu-id="84ed5-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
