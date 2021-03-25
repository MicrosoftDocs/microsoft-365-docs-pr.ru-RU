---
title: Получить API сведений о пользователях
description: Узнайте, как использовать API сведений о пользователях для получения объекта пользователя по ключу или имени пользователя в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, user, user information
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
ms.openlocfilehash: 1c5b8fa6e0f1fd887c857bd4e6451a5e59b708af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198545"
---
# <a name="get-user-information-api"></a><span data-ttu-id="dc27c-104">Получить API сведений о пользователях</span><span class="sxs-lookup"><span data-stu-id="dc27c-104">Get user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dc27c-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="dc27c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="dc27c-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="dc27c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dc27c-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="dc27c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> <span data-ttu-id="dc27c-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="dc27c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dc27c-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="dc27c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)
<span data-ttu-id="dc27c-110">Извлечение сущности пользователя по ключу (имя пользователя).</span><span class="sxs-lookup"><span data-stu-id="dc27c-110">Retrieve a User entity by key (user name).</span></span>

## <a name="permissions"></a><span data-ttu-id="dc27c-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="dc27c-111">Permissions</span></span>
<span data-ttu-id="dc27c-112">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="dc27c-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="dc27c-113">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="dc27c-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="dc27c-114">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="dc27c-114">Permission type</span></span> |   <span data-ttu-id="dc27c-115">Разрешение</span><span class="sxs-lookup"><span data-stu-id="dc27c-115">Permission</span></span>  |   <span data-ttu-id="dc27c-116">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="dc27c-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="dc27c-117">Для приложений</span><span class="sxs-lookup"><span data-stu-id="dc27c-117">Application</span></span> |   <span data-ttu-id="dc27c-118">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="dc27c-118">User.Read.All</span></span> | <span data-ttu-id="dc27c-119">'Read all user profiles'</span><span class="sxs-lookup"><span data-stu-id="dc27c-119">'Read all user profiles'</span></span>

## <a name="http-request"></a><span data-ttu-id="dc27c-120">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="dc27c-120">HTTP request</span></span>
```
GET /api/users/{id}/
```

## <a name="request-headers"></a><span data-ttu-id="dc27c-121">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="dc27c-121">Request headers</span></span>

<span data-ttu-id="dc27c-122">Имя</span><span class="sxs-lookup"><span data-stu-id="dc27c-122">Name</span></span> | <span data-ttu-id="dc27c-123">Тип</span><span class="sxs-lookup"><span data-stu-id="dc27c-123">Type</span></span> | <span data-ttu-id="dc27c-124">Описание</span><span class="sxs-lookup"><span data-stu-id="dc27c-124">Description</span></span>
:---|:---|:---
<span data-ttu-id="dc27c-125">Авторизация</span><span class="sxs-lookup"><span data-stu-id="dc27c-125">Authorization</span></span> | <span data-ttu-id="dc27c-126">Строка</span><span class="sxs-lookup"><span data-stu-id="dc27c-126">String</span></span> | <span data-ttu-id="dc27c-127">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="dc27c-127">Bearer {token}.</span></span> <span data-ttu-id="dc27c-128">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="dc27c-128">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="dc27c-129">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="dc27c-129">Request body</span></span>
<span data-ttu-id="dc27c-130">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="dc27c-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="dc27c-131">Отклик</span><span class="sxs-lookup"><span data-stu-id="dc27c-131">Response</span></span>
<span data-ttu-id="dc27c-132">При успешном и удобном пользователе — 200 ОК с [пользовательским](user.md) объектом в теле.</span><span class="sxs-lookup"><span data-stu-id="dc27c-132">If successful and user exists - 200 OK with [user](user.md) entity in the body.</span></span> <span data-ttu-id="dc27c-133">Если пользователя не существует - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="dc27c-133">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="dc27c-134">Пример</span><span class="sxs-lookup"><span data-stu-id="dc27c-134">Example</span></span>

<span data-ttu-id="dc27c-135">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="dc27c-135">**Request**</span></span>

<span data-ttu-id="dc27c-136">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="dc27c-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/users/user1
Content-type: application/json
```

<span data-ttu-id="dc27c-137">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="dc27c-137">**Response**</span></span>

<span data-ttu-id="dc27c-138">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="dc27c-138">Here is an example of the response.</span></span>


```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "user1",
    "firstSeen": "2018-08-02T00:00:00Z",
    "lastSeen": "2018-08-04T00:00:00Z",
    "mostPrevalentMachineId": null,
    "leastPrevalentMachineId": null,
    "logonTypes": "Network",
    "logOnMachinesCount": 3,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": null
}
```
