---
title: API индикаторов списка
description: Узнайте, как использовать API индикаторов списка для получения коллекции всех активных индикаторов в Microsoft Defender для конечной точки.
keywords: apis, public api, supported apis, Indicators collection
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 868fd141cda3b3d92464a2d9247780e0e74d6de8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198557"
---
# <a name="list-indicators-api"></a><span data-ttu-id="ced2d-104">API индикаторов списка</span><span class="sxs-lookup"><span data-stu-id="ced2d-104">List Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ced2d-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ced2d-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ced2d-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ced2d-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ced2d-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ced2d-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="ced2d-108">Описание API</span><span class="sxs-lookup"><span data-stu-id="ced2d-108">API description</span></span>
<span data-ttu-id="ced2d-109">Извлекает коллекцию всех активных [индикаторов.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="ced2d-109">Retrieves a collection of all active [Indicators](ti-indicator.md).</span></span>
<br><span data-ttu-id="ced2d-110">Поддерживает [запросы OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="ced2d-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="ced2d-111">Запрос OData поддерживается ```$filter``` на: ```indicatorValue``` , , , ```indicatorType``` и ```creationTimeDateTimeUtc``` ```createdBy``` ```action``` ```severity``` свойства.</span><span class="sxs-lookup"><span data-stu-id="ced2d-111">The OData's ```$filter``` query is supported on: ```indicatorValue```, ```indicatorType```, ```creationTimeDateTimeUtc```, ```createdBy```, ```action``` and ```severity``` properties.</span></span>
<br><span data-ttu-id="ced2d-112">Примеры запросов [OData в Microsoft Defender для конечной точки](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="ced2d-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="ced2d-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ced2d-113">Limitations</span></span>
1. <span data-ttu-id="ced2d-114">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="ced2d-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="ced2d-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="ced2d-115">Permissions</span></span>
<span data-ttu-id="ced2d-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="ced2d-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ced2d-117">Дополнительные новости, в том числе выбор разрешений, см. в [руб. Начало работы](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ced2d-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="ced2d-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="ced2d-118">Permission type</span></span> |   <span data-ttu-id="ced2d-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="ced2d-119">Permission</span></span>  |   <span data-ttu-id="ced2d-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="ced2d-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ced2d-121">Application</span><span class="sxs-lookup"><span data-stu-id="ced2d-121">Application</span></span> |   <span data-ttu-id="ced2d-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ced2d-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="ced2d-123">'Read and write Indicators'</span><span class="sxs-lookup"><span data-stu-id="ced2d-123">'Read and write Indicators'</span></span>
<span data-ttu-id="ced2d-124">Application</span><span class="sxs-lookup"><span data-stu-id="ced2d-124">Application</span></span> |   <span data-ttu-id="ced2d-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="ced2d-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="ced2d-126">'Read and write All Indicators'</span><span class="sxs-lookup"><span data-stu-id="ced2d-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="ced2d-127">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="ced2d-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="ced2d-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ced2d-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="ced2d-129">'Read and write Indicators'</span><span class="sxs-lookup"><span data-stu-id="ced2d-129">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="ced2d-130">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="ced2d-130">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="ced2d-131">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="ced2d-131">Request headers</span></span>

<span data-ttu-id="ced2d-132">Имя</span><span class="sxs-lookup"><span data-stu-id="ced2d-132">Name</span></span> | <span data-ttu-id="ced2d-133">Тип</span><span class="sxs-lookup"><span data-stu-id="ced2d-133">Type</span></span> | <span data-ttu-id="ced2d-134">Описание</span><span class="sxs-lookup"><span data-stu-id="ced2d-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="ced2d-135">Авторизация</span><span class="sxs-lookup"><span data-stu-id="ced2d-135">Authorization</span></span> | <span data-ttu-id="ced2d-136">Строка</span><span class="sxs-lookup"><span data-stu-id="ced2d-136">String</span></span> | <span data-ttu-id="ced2d-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ced2d-137">Bearer {token}.</span></span> <span data-ttu-id="ced2d-138">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="ced2d-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ced2d-139">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="ced2d-139">Request body</span></span>
<span data-ttu-id="ced2d-140">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="ced2d-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ced2d-141">Отклик</span><span class="sxs-lookup"><span data-stu-id="ced2d-141">Response</span></span>
<span data-ttu-id="ced2d-142">В случае успешной работы этот метод возвращает 200 код ответа Ok с набором сущностями [индикатора.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="ced2d-142">If successful, this method returns 200, Ok response code with a collection of [Indicator](ti-indicator.md) entities.</span></span>

>[!Note]
> <span data-ttu-id="ced2d-143">Если приложение имеет разрешение "Ti.ReadWrite.All", оно будет подвергаться воздействию всех индикаторов.</span><span class="sxs-lookup"><span data-stu-id="ced2d-143">If the Application has 'Ti.ReadWrite.All' permission, it will be exposed to all Indicators.</span></span> <span data-ttu-id="ced2d-144">В противном случае он будет подвергаться воздействию только созданных индикаторов.</span><span class="sxs-lookup"><span data-stu-id="ced2d-144">Otherwise, it will be exposed only to the Indicators it created.</span></span>

## <a name="example-1"></a><span data-ttu-id="ced2d-145">Пример 1:</span><span class="sxs-lookup"><span data-stu-id="ced2d-145">Example 1:</span></span>

<span data-ttu-id="ced2d-146">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="ced2d-146">**Request**</span></span>

<span data-ttu-id="ced2d-147">Вот пример запроса, который получает все индикаторы</span><span class="sxs-lookup"><span data-stu-id="ced2d-147">Here is an example of a request that gets all Indicators</span></span>

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

<span data-ttu-id="ced2d-148">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="ced2d-148">**Response**</span></span>

<span data-ttu-id="ced2d-149">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="ced2d-149">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "995",
            "indicatorValue": "12.13.14.15",
            "indicatorType": "IpAddress",
            "action": "Alert",
            "application": "demo-test",
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test",
            "rbacGroupNames": []
        },
        {
            "id": "996",
            "indicatorValue": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="ced2d-150">Пример 2:</span><span class="sxs-lookup"><span data-stu-id="ced2d-150">Example 2:</span></span>

<span data-ttu-id="ced2d-151">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="ced2d-151">**Request**</span></span>

<span data-ttu-id="ced2d-152">Вот пример запроса, который получает все индикаторы с действием AlertAndBlock.</span><span class="sxs-lookup"><span data-stu-id="ced2d-152">Here is an example of a request that gets all Indicators with 'AlertAndBlock' action</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

<span data-ttu-id="ced2d-153">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="ced2d-153">**Response**</span></span>

<span data-ttu-id="ced2d-154">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="ced2d-154">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "997",
            "indicatorValue": "111e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```
