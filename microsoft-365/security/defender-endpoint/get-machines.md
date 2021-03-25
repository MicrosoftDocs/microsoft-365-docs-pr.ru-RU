---
title: API машин списка
description: Узнайте, как использовать API машин Списка для получения коллекции машин, которые взаимодействовали с облаком ATP Microsoft Defender.
keywords: apis, graph api, supported apis, get, devices
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
ms.openlocfilehash: 23997cf4997ccfea8ee89a9b9ec5cc991dfa1ed0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200381"
---
# <a name="list-machines-api"></a><span data-ttu-id="646e2-104">API машин списка</span><span class="sxs-lookup"><span data-stu-id="646e2-104">List machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="646e2-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="646e2-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="646e2-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="646e2-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="646e2-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="646e2-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="646e2-108">Описание API</span><span class="sxs-lookup"><span data-stu-id="646e2-108">API description</span></span>
<span data-ttu-id="646e2-109">Извлекает коллекцию [машин,](machine.md) которые связывались с облаком Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="646e2-109">Retrieves a collection of [Machines](machine.md) that have communicated with  Microsoft Defender for Endpoint cloud.</span></span>
<br><span data-ttu-id="646e2-110">Поддерживает [запросы OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="646e2-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="646e2-111">Запрос OData поддерживается `$filter` на: `computerDnsName` , , , , и `lastSeen` `healthStatus` `osPlatform` `riskScore` `rbacGroupId` .</span><span class="sxs-lookup"><span data-stu-id="646e2-111">The OData's `$filter` query is supported on: `computerDnsName`, `lastSeen`, `healthStatus`, `osPlatform`, `riskScore` and `rbacGroupId`.</span></span>
<br><span data-ttu-id="646e2-112">Примеры запросов [OData](exposed-apis-odata-samples.md) с Defender для endpoint</span><span class="sxs-lookup"><span data-stu-id="646e2-112">See examples at [OData queries with Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="646e2-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="646e2-113">Limitations</span></span>
1. <span data-ttu-id="646e2-114">Устройства можно получить в последний раз в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="646e2-114">You can get devices last seen according to your configured retention period.</span></span>
2. <span data-ttu-id="646e2-115">Максимальный размер страницы — 10 000.</span><span class="sxs-lookup"><span data-stu-id="646e2-115">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="646e2-116">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="646e2-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="646e2-117">Разрешения</span><span class="sxs-lookup"><span data-stu-id="646e2-117">Permissions</span></span>

<span data-ttu-id="646e2-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="646e2-118">Permission type</span></span> |   <span data-ttu-id="646e2-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="646e2-119">Permission</span></span>  |   <span data-ttu-id="646e2-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="646e2-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="646e2-121">Application</span><span class="sxs-lookup"><span data-stu-id="646e2-121">Application</span></span> |   <span data-ttu-id="646e2-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="646e2-122">Machine.Read.All</span></span> |  <span data-ttu-id="646e2-123">'Read all machine profiles'</span><span class="sxs-lookup"><span data-stu-id="646e2-123">'Read all machine profiles'</span></span>
<span data-ttu-id="646e2-124">Application</span><span class="sxs-lookup"><span data-stu-id="646e2-124">Application</span></span> |   <span data-ttu-id="646e2-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="646e2-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="646e2-126">'Read and write all machine information'</span><span class="sxs-lookup"><span data-stu-id="646e2-126">'Read and write all machine information'</span></span>
<span data-ttu-id="646e2-127">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="646e2-127">Delegated (work or school account)</span></span> | <span data-ttu-id="646e2-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="646e2-128">Machine.Read</span></span> | <span data-ttu-id="646e2-129">'Read machine information'</span><span class="sxs-lookup"><span data-stu-id="646e2-129">'Read machine information'</span></span>
<span data-ttu-id="646e2-130">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="646e2-130">Delegated (work or school account)</span></span> | <span data-ttu-id="646e2-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="646e2-131">Machine.ReadWrite</span></span> | <span data-ttu-id="646e2-132">'Read and write machine information'</span><span class="sxs-lookup"><span data-stu-id="646e2-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="646e2-133">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="646e2-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="646e2-134">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="646e2-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="646e2-135">Ответ будет включать только устройства, к которые пользователь имеет доступ на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="646e2-135">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="646e2-136">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="646e2-136">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a><span data-ttu-id="646e2-137">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="646e2-137">Request headers</span></span>

<span data-ttu-id="646e2-138">Имя</span><span class="sxs-lookup"><span data-stu-id="646e2-138">Name</span></span> | <span data-ttu-id="646e2-139">Тип</span><span class="sxs-lookup"><span data-stu-id="646e2-139">Type</span></span> | <span data-ttu-id="646e2-140">Описание</span><span class="sxs-lookup"><span data-stu-id="646e2-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="646e2-141">Авторизация</span><span class="sxs-lookup"><span data-stu-id="646e2-141">Authorization</span></span> | <span data-ttu-id="646e2-142">Строка</span><span class="sxs-lookup"><span data-stu-id="646e2-142">String</span></span> | <span data-ttu-id="646e2-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="646e2-143">Bearer {token}.</span></span> <span data-ttu-id="646e2-144">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="646e2-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="646e2-145">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="646e2-145">Request body</span></span>
<span data-ttu-id="646e2-146">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="646e2-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="646e2-147">Отклик</span><span class="sxs-lookup"><span data-stu-id="646e2-147">Response</span></span>
<span data-ttu-id="646e2-148">Если успешно и машины существуют — 200 ОК со списком машинных [](machine.md) сущностями в теле.</span><span class="sxs-lookup"><span data-stu-id="646e2-148">If successful and machines exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="646e2-149">Если нет недавних машин - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="646e2-149">If no recent machines - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="646e2-150">Пример</span><span class="sxs-lookup"><span data-stu-id="646e2-150">Example</span></span>

<span data-ttu-id="646e2-151">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="646e2-151">**Request**</span></span>

<span data-ttu-id="646e2-152">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="646e2-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

<span data-ttu-id="646e2-153">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="646e2-153">**Response**</span></span>

<span data-ttu-id="646e2-154">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="646e2-154">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="646e2-155">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="646e2-155">Related topics</span></span>
- [<span data-ttu-id="646e2-156">Запросы OData в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="646e2-156">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)