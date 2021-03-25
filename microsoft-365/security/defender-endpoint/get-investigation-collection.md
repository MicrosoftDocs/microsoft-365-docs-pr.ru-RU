---
title: API списков расследований
description: Используйте этот API для создания вызовов, связанных с сбором расследований
keywords: apis, graph api, supported apis, Investigations collection
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 9ad1216a05846b48bff4186c7e6f39e9da3623b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167119"
---
# <a name="list-investigations-api"></a><span data-ttu-id="0a921-104">API списков расследований</span><span class="sxs-lookup"><span data-stu-id="0a921-104">List Investigations API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0a921-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0a921-105">**Applies to:**</span></span>
- [<span data-ttu-id="0a921-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0a921-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0a921-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a921-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0a921-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="0a921-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0a921-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="0a921-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="0a921-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="0a921-110">API description</span></span>
<span data-ttu-id="0a921-111">Извлекает коллекцию [исследований.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="0a921-111">Retrieves a collection of [Investigations](investigation.md).</span></span>
<br><span data-ttu-id="0a921-112">Поддерживает [запросы OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="0a921-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="0a921-113">Запрос OData поддерживается ```$filter``` на: ```startTime``` и ```state``` ```machineId``` ```triggeringAlertId``` свойствах.</span><span class="sxs-lookup"><span data-stu-id="0a921-113">The OData's ```$filter``` query is supported on: ```startTime```, ```state```, ```machineId``` and ```triggeringAlertId``` properties.</span></span>
<br><span data-ttu-id="0a921-114">Примеры запросов [OData в Microsoft Defender для конечной точки](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="0a921-114">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="0a921-115">Ограничения</span><span class="sxs-lookup"><span data-stu-id="0a921-115">Limitations</span></span>
1. <span data-ttu-id="0a921-116">Максимальный размер страницы — 10 000.</span><span class="sxs-lookup"><span data-stu-id="0a921-116">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="0a921-117">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="0a921-117">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="0a921-118">Разрешения</span><span class="sxs-lookup"><span data-stu-id="0a921-118">Permissions</span></span>
<span data-ttu-id="0a921-119">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="0a921-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0a921-120">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0a921-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="0a921-121">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="0a921-121">Permission type</span></span> |   <span data-ttu-id="0a921-122">Разрешение</span><span class="sxs-lookup"><span data-stu-id="0a921-122">Permission</span></span>  |   <span data-ttu-id="0a921-123">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="0a921-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0a921-124">Приложение</span><span class="sxs-lookup"><span data-stu-id="0a921-124">Application</span></span> |   <span data-ttu-id="0a921-125">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="0a921-125">Alert.Read.All</span></span> |    <span data-ttu-id="0a921-126">'Read all alerts'</span><span class="sxs-lookup"><span data-stu-id="0a921-126">'Read all alerts'</span></span>
<span data-ttu-id="0a921-127">Приложение</span><span class="sxs-lookup"><span data-stu-id="0a921-127">Application</span></span> |   <span data-ttu-id="0a921-128">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="0a921-128">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="0a921-129">'Read and write all alerts'</span><span class="sxs-lookup"><span data-stu-id="0a921-129">'Read and write all alerts'</span></span>
<span data-ttu-id="0a921-130">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="0a921-130">Delegated (work or school account)</span></span> | <span data-ttu-id="0a921-131">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="0a921-131">Alert.Read</span></span> | <span data-ttu-id="0a921-132">'Read alerts'</span><span class="sxs-lookup"><span data-stu-id="0a921-132">'Read alerts'</span></span>
<span data-ttu-id="0a921-133">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="0a921-133">Delegated (work or school account)</span></span> | <span data-ttu-id="0a921-134">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0a921-134">Alert.ReadWrite</span></span> | <span data-ttu-id="0a921-135">'Read and write alerts'</span><span class="sxs-lookup"><span data-stu-id="0a921-135">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="0a921-136">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="0a921-136">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="0a921-137">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="0a921-137">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="0a921-138">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="0a921-138">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a><span data-ttu-id="0a921-139">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="0a921-139">Request headers</span></span>

<span data-ttu-id="0a921-140">Имя</span><span class="sxs-lookup"><span data-stu-id="0a921-140">Name</span></span> | <span data-ttu-id="0a921-141">Тип</span><span class="sxs-lookup"><span data-stu-id="0a921-141">Type</span></span> | <span data-ttu-id="0a921-142">Описание</span><span class="sxs-lookup"><span data-stu-id="0a921-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="0a921-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="0a921-143">Authorization</span></span> | <span data-ttu-id="0a921-144">Строка</span><span class="sxs-lookup"><span data-stu-id="0a921-144">String</span></span> | <span data-ttu-id="0a921-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="0a921-145">Bearer {token}.</span></span> <span data-ttu-id="0a921-146">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="0a921-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0a921-147">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="0a921-147">Request body</span></span>
<span data-ttu-id="0a921-148">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="0a921-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0a921-149">Отклик</span><span class="sxs-lookup"><span data-stu-id="0a921-149">Response</span></span>
<span data-ttu-id="0a921-150">В случае успешной работы этот метод возвращает 200 код ответа Ok с набором [сущностями Investigations.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="0a921-150">If successful, this method returns 200, Ok response code with a collection of [Investigations](investigation.md) entities.</span></span>


## <a name="example"></a><span data-ttu-id="0a921-151">Пример</span><span class="sxs-lookup"><span data-stu-id="0a921-151">Example</span></span>

<span data-ttu-id="0a921-152">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="0a921-152">**Request**</span></span>

<span data-ttu-id="0a921-153">Вот пример запроса на все исследования:</span><span class="sxs-lookup"><span data-stu-id="0a921-153">Here is an example of a request to get all investigations:</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

<span data-ttu-id="0a921-154">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="0a921-154">**Response**</span></span>

<span data-ttu-id="0a921-155">Вот пример ответа:</span><span class="sxs-lookup"><span data-stu-id="0a921-155">Here is an example of the response:</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
