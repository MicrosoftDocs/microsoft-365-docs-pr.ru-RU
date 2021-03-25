---
title: Получить сведения о пользователях, связанных с оповещением
description: Узнайте, как использовать API сведений о пользователях, связанных с оповещением, для получения пользователя, связанного с определенным оповещением в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, alert, information, related, user
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
ms.openlocfilehash: aee3c6fb381341c6823fbcb6766c0b761cb3413d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166980"
---
# <a name="get-alert-related-user-information-api"></a><span data-ttu-id="12858-104">Получить API сведений о пользователях, связанных с оповещением</span><span class="sxs-lookup"><span data-stu-id="12858-104">Get alert related user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="12858-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="12858-105">**Applies to:**</span></span>
- [<span data-ttu-id="12858-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="12858-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="12858-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12858-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="12858-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="12858-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="12858-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="12858-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="12858-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="12858-110">API description</span></span>
<span data-ttu-id="12858-111">Извлекает пользователя, связанного с определенным оповещением.</span><span class="sxs-lookup"><span data-stu-id="12858-111">Retrieves the User related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="12858-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="12858-112">Limitations</span></span>
1. <span data-ttu-id="12858-113">Вы можете запрашивать последние обновления оповещений в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="12858-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="12858-114">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="12858-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="12858-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="12858-115">Permissions</span></span>
<span data-ttu-id="12858-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="12858-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="12858-117">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="12858-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="12858-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="12858-118">Permission type</span></span> |   <span data-ttu-id="12858-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="12858-119">Permission</span></span>  |   <span data-ttu-id="12858-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="12858-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="12858-121">Для приложений</span><span class="sxs-lookup"><span data-stu-id="12858-121">Application</span></span> |   <span data-ttu-id="12858-122">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="12858-122">User.Read.All</span></span> | <span data-ttu-id="12858-123">'Read user profiles'</span><span class="sxs-lookup"><span data-stu-id="12858-123">'Read user profiles'</span></span>
<span data-ttu-id="12858-124">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="12858-124">Delegated (work or school account)</span></span> | <span data-ttu-id="12858-125">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="12858-125">User.Read.All</span></span> | <span data-ttu-id="12858-126">'Read user profiles'</span><span class="sxs-lookup"><span data-stu-id="12858-126">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="12858-127">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="12858-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="12858-128">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="12858-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="12858-129">Пользователь должен иметь доступ к устройству, связанному с оповещением, на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="12858-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="12858-130">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="12858-130">HTTP request</span></span>
```
GET /api/alerts/{id}/user
```

## <a name="request-headers"></a><span data-ttu-id="12858-131">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="12858-131">Request headers</span></span>

<span data-ttu-id="12858-132">Имя</span><span class="sxs-lookup"><span data-stu-id="12858-132">Name</span></span> | <span data-ttu-id="12858-133">Тип</span><span class="sxs-lookup"><span data-stu-id="12858-133">Type</span></span> | <span data-ttu-id="12858-134">Описание</span><span class="sxs-lookup"><span data-stu-id="12858-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="12858-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="12858-135">Authorization</span></span> | <span data-ttu-id="12858-136">Строка</span><span class="sxs-lookup"><span data-stu-id="12858-136">String</span></span> | <span data-ttu-id="12858-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="12858-137">Bearer {token}.</span></span> <span data-ttu-id="12858-138">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="12858-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="12858-139">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="12858-139">Request body</span></span>
<span data-ttu-id="12858-140">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="12858-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="12858-141">Отклик</span><span class="sxs-lookup"><span data-stu-id="12858-141">Response</span></span>
<span data-ttu-id="12858-142">При успешном и оповещении пользователя — 200 ОК с пользователем в теле.</span><span class="sxs-lookup"><span data-stu-id="12858-142">If successful and alert and a user exists - 200 OK with user in the body.</span></span> <span data-ttu-id="12858-143">Если оповещение или пользователь не найден - 404 Не найден.</span><span class="sxs-lookup"><span data-stu-id="12858-143">If alert or user not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="12858-144">Пример</span><span class="sxs-lookup"><span data-stu-id="12858-144">Example</span></span>

<span data-ttu-id="12858-145">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="12858-145">**Request**</span></span>

<span data-ttu-id="12858-146">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="12858-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/user
```

<span data-ttu-id="12858-147">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="12858-147">**Response**</span></span>

<span data-ttu-id="12858-148">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="12858-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "contoso\\user1",
    "accountName": "user1",
    "accountDomain": "contoso",
    "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
    "firstSeen": "2019-12-08T06:33:39Z",
    "lastSeen": "2020-01-05T06:58:34Z",
    "mostPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "leastPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "logonTypes": "Network",
    "logOnMachinesCount": 1,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": false
}
```
