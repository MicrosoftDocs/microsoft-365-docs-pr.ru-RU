---
title: Get machine by ID API
description: Узнайте, как использовать машину Get с помощью API ID для получения компьютера по его ID-имени устройства или имени компьютера в Microsoft Defender для конечной точки.
keywords: apis, api graph, supported apis, get, devices, entity, id
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
ms.openlocfilehash: 29423230d0d8d4baaa1acca9a3661dc3436f303d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200102"
---
# <a name="get-machine-by-id-api"></a><span data-ttu-id="b24dd-104">Get machine by ID API</span><span class="sxs-lookup"><span data-stu-id="b24dd-104">Get machine by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b24dd-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b24dd-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>


> <span data-ttu-id="b24dd-106">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b24dd-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b24dd-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b24dd-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b24dd-108">Описание API</span><span class="sxs-lookup"><span data-stu-id="b24dd-108">API description</span></span>
<span data-ttu-id="b24dd-109">Извлекает определенную [машину](machine.md) по ее ID устройства или имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="b24dd-109">Retrieves specific [Machine](machine.md) by its device ID or computer name.</span></span>


## <a name="limitations"></a><span data-ttu-id="b24dd-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b24dd-110">Limitations</span></span>
1. <span data-ttu-id="b24dd-111">Устройства можно получить в последний раз в соответствии с настроенной политикой хранения.</span><span class="sxs-lookup"><span data-stu-id="b24dd-111">You can get devices last seen according to your configured retention policy.</span></span>
2. <span data-ttu-id="b24dd-112">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="b24dd-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="b24dd-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="b24dd-113">Permissions</span></span>
<span data-ttu-id="b24dd-114">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="b24dd-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b24dd-115">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b24dd-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b24dd-116">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="b24dd-116">Permission type</span></span> |   <span data-ttu-id="b24dd-117">Разрешение</span><span class="sxs-lookup"><span data-stu-id="b24dd-117">Permission</span></span>  |   <span data-ttu-id="b24dd-118">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="b24dd-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b24dd-119">Application</span><span class="sxs-lookup"><span data-stu-id="b24dd-119">Application</span></span> |   <span data-ttu-id="b24dd-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="b24dd-120">Machine.Read.All</span></span> |  <span data-ttu-id="b24dd-121">'Read all machine profiles'</span><span class="sxs-lookup"><span data-stu-id="b24dd-121">'Read all machine profiles'</span></span>
<span data-ttu-id="b24dd-122">Application</span><span class="sxs-lookup"><span data-stu-id="b24dd-122">Application</span></span> |   <span data-ttu-id="b24dd-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b24dd-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="b24dd-124">'Read and write all machine information'</span><span class="sxs-lookup"><span data-stu-id="b24dd-124">'Read and write all machine information'</span></span>
<span data-ttu-id="b24dd-125">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="b24dd-125">Delegated (work or school account)</span></span> | <span data-ttu-id="b24dd-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="b24dd-126">Machine.Read</span></span> | <span data-ttu-id="b24dd-127">'Read machine information'</span><span class="sxs-lookup"><span data-stu-id="b24dd-127">'Read machine information'</span></span>
<span data-ttu-id="b24dd-128">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="b24dd-128">Delegated (work or school account)</span></span> | <span data-ttu-id="b24dd-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b24dd-129">Machine.ReadWrite</span></span> | <span data-ttu-id="b24dd-130">'Read and write machine information'</span><span class="sxs-lookup"><span data-stu-id="b24dd-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="b24dd-131">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="b24dd-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b24dd-132">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="b24dd-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b24dd-133">Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="b24dd-133">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="b24dd-134">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="b24dd-134">HTTP request</span></span>
```http
GET /api/machines/{id}
```

## <a name="request-headers"></a><span data-ttu-id="b24dd-135">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="b24dd-135">Request headers</span></span>

<span data-ttu-id="b24dd-136">Имя</span><span class="sxs-lookup"><span data-stu-id="b24dd-136">Name</span></span> | <span data-ttu-id="b24dd-137">Тип</span><span class="sxs-lookup"><span data-stu-id="b24dd-137">Type</span></span> | <span data-ttu-id="b24dd-138">Описание</span><span class="sxs-lookup"><span data-stu-id="b24dd-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="b24dd-139">Авторизация</span><span class="sxs-lookup"><span data-stu-id="b24dd-139">Authorization</span></span> | <span data-ttu-id="b24dd-140">Строка</span><span class="sxs-lookup"><span data-stu-id="b24dd-140">String</span></span> | <span data-ttu-id="b24dd-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b24dd-141">Bearer {token}.</span></span> <span data-ttu-id="b24dd-142">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="b24dd-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b24dd-143">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="b24dd-143">Request body</span></span>
<span data-ttu-id="b24dd-144">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="b24dd-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b24dd-145">Отклик</span><span class="sxs-lookup"><span data-stu-id="b24dd-145">Response</span></span>
<span data-ttu-id="b24dd-146">При успешном и устройстве существует — 200 ОК с [машинным](machine.md) объектом в теле.</span><span class="sxs-lookup"><span data-stu-id="b24dd-146">If successful and device exists - 200 OK with the [machine](machine.md) entity in the body.</span></span>
<span data-ttu-id="b24dd-147">Если машина с указанным ИД не найдена - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="b24dd-147">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="b24dd-148">Пример</span><span class="sxs-lookup"><span data-stu-id="b24dd-148">Example</span></span>

<span data-ttu-id="b24dd-149">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="b24dd-149">**Request**</span></span>

<span data-ttu-id="b24dd-150">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="b24dd-150">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07
```

<span data-ttu-id="b24dd-151">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="b24dd-151">**Response**</span></span>

<span data-ttu-id="b24dd-152">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="b24dd-152">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machine",
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

```
