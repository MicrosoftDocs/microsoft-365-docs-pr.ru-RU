---
title: Получите API пользователей с логотипами машин
description: Узнайте, как использовать API пользователей с логотипом get machine для получения коллекции зарегистрированных пользователей на устройстве в Microsoft Defender for Endpoint.
keywords: apis, api graph, supported apis, get, device, log on, users
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
ms.openlocfilehash: 1c81d2978677b751a8085f88b5c4732fd4a5a247
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770053"
---
# <a name="get-machine-logon-users-api"></a><span data-ttu-id="56c07-104">Получите API пользователей с логотипами машин</span><span class="sxs-lookup"><span data-stu-id="56c07-104">Get machine logon users API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="56c07-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="56c07-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="56c07-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="56c07-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="56c07-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="56c07-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="56c07-108">Описание API</span><span class="sxs-lookup"><span data-stu-id="56c07-108">API description</span></span>
<span data-ttu-id="56c07-109">Извлекает коллекцию в журнале пользователей на определенном устройстве.</span><span class="sxs-lookup"><span data-stu-id="56c07-109">Retrieves a collection of logged on users on a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="56c07-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="56c07-110">Limitations</span></span>
1. <span data-ttu-id="56c07-111">Вы можете запрашивать последние обновления оповещений в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="56c07-111">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="56c07-112">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="56c07-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="56c07-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="56c07-113">Permissions</span></span>
<span data-ttu-id="56c07-114">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="56c07-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="56c07-115">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="56c07-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="56c07-116">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="56c07-116">Permission type</span></span> |   <span data-ttu-id="56c07-117">Разрешение</span><span class="sxs-lookup"><span data-stu-id="56c07-117">Permission</span></span>  |   <span data-ttu-id="56c07-118">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="56c07-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="56c07-119">Для приложений</span><span class="sxs-lookup"><span data-stu-id="56c07-119">Application</span></span> |   <span data-ttu-id="56c07-120">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="56c07-120">User.Read.All</span></span> | <span data-ttu-id="56c07-121">'Read user profiles'</span><span class="sxs-lookup"><span data-stu-id="56c07-121">'Read user profiles'</span></span>
<span data-ttu-id="56c07-122">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="56c07-122">Delegated (work or school account)</span></span> | <span data-ttu-id="56c07-123">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="56c07-123">User.Read.All</span></span> | <span data-ttu-id="56c07-124">'Read user profiles'</span><span class="sxs-lookup"><span data-stu-id="56c07-124">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="56c07-125">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="56c07-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="56c07-126">У пользователя должно быть по крайней мере следующее разрешение на роль: "Просмотр данных".</span><span class="sxs-lookup"><span data-stu-id="56c07-126">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="56c07-127">Дополнительные сведения см. в [дополнительных сведениях о создании и управлении ролями](user-roles.md) )</span><span class="sxs-lookup"><span data-stu-id="56c07-127">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="56c07-128">Ответ будет включать пользователей только в том случае, если устройство отображается пользователю в зависимости от параметров группы устройств.</span><span class="sxs-lookup"><span data-stu-id="56c07-128">Response will include users only if the device is visible to the user, based on device group settings.</span></span> <span data-ttu-id="56c07-129">Дополнительные сведения см. в [дополнительных сведениях о создании и управлении группами устройств.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="56c07-129">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="56c07-130">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="56c07-130">HTTP request</span></span>
```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a><span data-ttu-id="56c07-131">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="56c07-131">Request headers</span></span>

<span data-ttu-id="56c07-132">Имя</span><span class="sxs-lookup"><span data-stu-id="56c07-132">Name</span></span> | <span data-ttu-id="56c07-133">Тип</span><span class="sxs-lookup"><span data-stu-id="56c07-133">Type</span></span> | <span data-ttu-id="56c07-134">Описание</span><span class="sxs-lookup"><span data-stu-id="56c07-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="56c07-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="56c07-135">Authorization</span></span> | <span data-ttu-id="56c07-136">String</span><span class="sxs-lookup"><span data-stu-id="56c07-136">String</span></span> | <span data-ttu-id="56c07-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="56c07-137">Bearer {token}.</span></span> <span data-ttu-id="56c07-138">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="56c07-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="56c07-139">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="56c07-139">Request body</span></span>
<span data-ttu-id="56c07-140">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="56c07-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="56c07-141">Отклик</span><span class="sxs-lookup"><span data-stu-id="56c07-141">Response</span></span>
<span data-ttu-id="56c07-142">При успешном и устройстве существует 200 ОК со списком пользовательских [](user.md) сущностями в теле.</span><span class="sxs-lookup"><span data-stu-id="56c07-142">If successful and device exists - 200 OK with list of [user](user.md) entities in the body.</span></span> <span data-ttu-id="56c07-143">Если устройство не найдено - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="56c07-143">If device was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="56c07-144">Пример</span><span class="sxs-lookup"><span data-stu-id="56c07-144">Example</span></span>

<span data-ttu-id="56c07-145">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="56c07-145">**Request**</span></span>

<span data-ttu-id="56c07-146">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="56c07-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

<span data-ttu-id="56c07-147">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="56c07-147">**Response**</span></span>

<span data-ttu-id="56c07-148">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="56c07-148">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
