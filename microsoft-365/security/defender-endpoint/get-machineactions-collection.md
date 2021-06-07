---
title: API machineActions списка
description: Узнайте, как использовать API машины списка для получения коллекции действий машин в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, machineaction collection
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2ee9a4e29dded3e299ffbb2c2997fd02f32d1abf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771121"
---
# <a name="list-machineactions-api"></a><span data-ttu-id="d06a8-104">API списка machineActions</span><span class="sxs-lookup"><span data-stu-id="d06a8-104">List MachineActions API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d06a8-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d06a8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="d06a8-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d06a8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d06a8-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d06a8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="d06a8-108">Описание API</span><span class="sxs-lookup"><span data-stu-id="d06a8-108">API description</span></span>
<span data-ttu-id="d06a8-109">Извлекает коллекцию [машинных действий.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="d06a8-109">Retrieves a collection of [Machine Actions](machineaction.md).</span></span>
<br><span data-ttu-id="d06a8-110">Поддерживает [запросы OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="d06a8-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="d06a8-111">Запрос OData поддерживается ```$filter``` на: ```status``` , , ```machineId``` и ```type``` ```requestor``` ```creationDateTimeUtc``` свойства.</span><span class="sxs-lookup"><span data-stu-id="d06a8-111">The OData's ```$filter``` query is supported on: ```status```, ```machineId```, ```type```, ```requestor``` and ```creationDateTimeUtc``` properties.</span></span>
<br><span data-ttu-id="d06a8-112">Примеры запросов [OData в Microsoft Defender для конечной точки](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="d06a8-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="d06a8-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d06a8-113">Limitations</span></span>
1. <span data-ttu-id="d06a8-114">Максимальный размер страницы — 10 000.</span><span class="sxs-lookup"><span data-stu-id="d06a8-114">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="d06a8-115">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="d06a8-115">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="d06a8-116">Разрешения</span><span class="sxs-lookup"><span data-stu-id="d06a8-116">Permissions</span></span>
<span data-ttu-id="d06a8-117">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="d06a8-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d06a8-118">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d06a8-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d06a8-119">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="d06a8-119">Permission type</span></span> |   <span data-ttu-id="d06a8-120">Разрешение</span><span class="sxs-lookup"><span data-stu-id="d06a8-120">Permission</span></span>  |   <span data-ttu-id="d06a8-121">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="d06a8-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d06a8-122">Приложение</span><span class="sxs-lookup"><span data-stu-id="d06a8-122">Application</span></span> |   <span data-ttu-id="d06a8-123">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="d06a8-123">Machine.Read.All</span></span> |  <span data-ttu-id="d06a8-124">'Read all machine profiles'</span><span class="sxs-lookup"><span data-stu-id="d06a8-124">'Read all machine profiles'</span></span>
<span data-ttu-id="d06a8-125">Приложение</span><span class="sxs-lookup"><span data-stu-id="d06a8-125">Application</span></span> |   <span data-ttu-id="d06a8-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d06a8-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="d06a8-127">'Read and write all machine information'</span><span class="sxs-lookup"><span data-stu-id="d06a8-127">'Read and write all machine information'</span></span>
<span data-ttu-id="d06a8-128">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="d06a8-128">Delegated (work or school account)</span></span> | <span data-ttu-id="d06a8-129">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="d06a8-129">Machine.Read</span></span> | <span data-ttu-id="d06a8-130">'Read machine information'</span><span class="sxs-lookup"><span data-stu-id="d06a8-130">'Read machine information'</span></span>
<span data-ttu-id="d06a8-131">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="d06a8-131">Delegated (work or school account)</span></span> | <span data-ttu-id="d06a8-132">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d06a8-132">Machine.ReadWrite</span></span> | <span data-ttu-id="d06a8-133">'Read and write machine information'</span><span class="sxs-lookup"><span data-stu-id="d06a8-133">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="d06a8-134">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="d06a8-134">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d06a8-135">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="d06a8-135">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d06a8-136">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="d06a8-136">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

## <a name="request-headers"></a><span data-ttu-id="d06a8-137">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="d06a8-137">Request headers</span></span>

<span data-ttu-id="d06a8-138">Имя</span><span class="sxs-lookup"><span data-stu-id="d06a8-138">Name</span></span> | <span data-ttu-id="d06a8-139">Тип</span><span class="sxs-lookup"><span data-stu-id="d06a8-139">Type</span></span> | <span data-ttu-id="d06a8-140">Описание</span><span class="sxs-lookup"><span data-stu-id="d06a8-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="d06a8-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="d06a8-141">Authorization</span></span> | <span data-ttu-id="d06a8-142">String</span><span class="sxs-lookup"><span data-stu-id="d06a8-142">String</span></span> | <span data-ttu-id="d06a8-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d06a8-143">Bearer {token}.</span></span> <span data-ttu-id="d06a8-144">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="d06a8-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="d06a8-145">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="d06a8-145">Request body</span></span>
<span data-ttu-id="d06a8-146">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="d06a8-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d06a8-147">Отклик</span><span class="sxs-lookup"><span data-stu-id="d06a8-147">Response</span></span>
<span data-ttu-id="d06a8-148">В случае успешной работы этот метод возвращает 200 код ответа Ok с набором [сущностями machineAction.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="d06a8-148">If successful, this method returns 200, Ok response code with a collection of [machineAction](machineaction.md) entities.</span></span>


## <a name="example-1"></a><span data-ttu-id="d06a8-149">Пример 1</span><span class="sxs-lookup"><span data-stu-id="d06a8-149">Example 1</span></span>

<span data-ttu-id="d06a8-150">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="d06a8-150">**Request**</span></span>

<span data-ttu-id="d06a8-151">Вот пример запроса в организации, которая имеет три MachineActions.</span><span class="sxs-lookup"><span data-stu-id="d06a8-151">Here is an example of the request on an organization that has three MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

<span data-ttu-id="d06a8-152">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="d06a8-152">**Response**</span></span>

<span data-ttu-id="d06a8-153">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="d06a8-153">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        },
        {
            "id": "44cffc15-0e3d-4cbf-96aa-bf76f9b27f5e",
            "type": "StopAndQuarantineFile",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:15:40.6052029Z",
            "lastUpdateTimeUtc": "2018-12-04T12:16:14.2899973Z",
            "relatedFileInfo": {
                "fileIdentifier": "a0c659857ccbe457fdaf5fe21d54efdcbf6f6508",
                "fileIdentifierType": "Sha1"
            }
        }
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="d06a8-154">Пример 2</span><span class="sxs-lookup"><span data-stu-id="d06a8-154">Example 2</span></span>

<span data-ttu-id="d06a8-155">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="d06a8-155">**Request**</span></span>

<span data-ttu-id="d06a8-156">Вот пример запроса, который фильтрует MachineActions с помощью машинного ИД и отображает последние два machineActions.</span><span class="sxs-lookup"><span data-stu-id="d06a8-156">Here is an example of a request that filters the MachineActions by machine ID and shows the latest two MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions?$filter=machineId eq 'f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f'&$top=2
```

<span data-ttu-id="d06a8-157">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="d06a8-157">**Response**</span></span>

<span data-ttu-id="d06a8-158">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="d06a8-158">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="d06a8-159">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="d06a8-159">Related topics</span></span>
- [<span data-ttu-id="d06a8-160">Запросы OData в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d06a8-160">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
