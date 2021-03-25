---
title: Получать сведения о машине, связанной с оповещением
description: Извлечение всех устройств, связанных с определенным оповещением с помощью Microsoft Defender для конечной точки.
keywords: apis, api graph, supported apis, get alert information, alert information, related device
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
ms.openlocfilehash: 70ce6adce3e14be7ee440b96587b8f9402c0b99f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166987"
---
# <a name="get-alert-related-machine-information-api"></a><span data-ttu-id="68f27-104">Получить API сведений о машинах, связанных с оповещением</span><span class="sxs-lookup"><span data-stu-id="68f27-104">Get alert related machine information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="68f27-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="68f27-105">**Applies to:**</span></span>
- [<span data-ttu-id="68f27-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="68f27-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="68f27-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68f27-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="68f27-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="68f27-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="68f27-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="68f27-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="68f27-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="68f27-110">API description</span></span>
<span data-ttu-id="68f27-111">Извлекает [устройство,](machine.md) связанное с определенным оповещением.</span><span class="sxs-lookup"><span data-stu-id="68f27-111">Retrieves [Device](machine.md) related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="68f27-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="68f27-112">Limitations</span></span>
1. <span data-ttu-id="68f27-113">Вы можете запрашивать последние обновления оповещений в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="68f27-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="68f27-114">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="68f27-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="68f27-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="68f27-115">Permissions</span></span>
<span data-ttu-id="68f27-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="68f27-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="68f27-117">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="68f27-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="68f27-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="68f27-118">Permission type</span></span> |   <span data-ttu-id="68f27-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="68f27-119">Permission</span></span>  |   <span data-ttu-id="68f27-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="68f27-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="68f27-121">Приложение</span><span class="sxs-lookup"><span data-stu-id="68f27-121">Application</span></span> |   <span data-ttu-id="68f27-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="68f27-122">Machine.Read.All</span></span> |  <span data-ttu-id="68f27-123">'Read all machine information'</span><span class="sxs-lookup"><span data-stu-id="68f27-123">'Read all machine information'</span></span>
<span data-ttu-id="68f27-124">Приложение</span><span class="sxs-lookup"><span data-stu-id="68f27-124">Application</span></span> |   <span data-ttu-id="68f27-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="68f27-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="68f27-126">'Read and write all machine information'</span><span class="sxs-lookup"><span data-stu-id="68f27-126">'Read and write all machine information'</span></span>
<span data-ttu-id="68f27-127">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="68f27-127">Delegated (work or school account)</span></span> | <span data-ttu-id="68f27-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="68f27-128">Machine.Read</span></span> | <span data-ttu-id="68f27-129">'Read machine information'</span><span class="sxs-lookup"><span data-stu-id="68f27-129">'Read machine information'</span></span>
<span data-ttu-id="68f27-130">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="68f27-130">Delegated (work or school account)</span></span> | <span data-ttu-id="68f27-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="68f27-131">Machine.ReadWrite</span></span> | <span data-ttu-id="68f27-132">'Read and write machine information'</span><span class="sxs-lookup"><span data-stu-id="68f27-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="68f27-133">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="68f27-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="68f27-134">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="68f27-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="68f27-135">Пользователь должен иметь доступ к устройству, связанному с оповещением, на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="68f27-135">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="68f27-136">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="68f27-136">HTTP request</span></span>

```http
GET /api/alerts/{id}/machine
```

## <a name="request-headers"></a><span data-ttu-id="68f27-137">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="68f27-137">Request headers</span></span>

<span data-ttu-id="68f27-138">Имя</span><span class="sxs-lookup"><span data-stu-id="68f27-138">Name</span></span> | <span data-ttu-id="68f27-139">Тип</span><span class="sxs-lookup"><span data-stu-id="68f27-139">Type</span></span> | <span data-ttu-id="68f27-140">Описание</span><span class="sxs-lookup"><span data-stu-id="68f27-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="68f27-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="68f27-141">Authorization</span></span> | <span data-ttu-id="68f27-142">Строка</span><span class="sxs-lookup"><span data-stu-id="68f27-142">String</span></span> | <span data-ttu-id="68f27-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="68f27-143">Bearer {token}.</span></span> <span data-ttu-id="68f27-144">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="68f27-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="68f27-145">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="68f27-145">Request body</span></span>
<span data-ttu-id="68f27-146">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="68f27-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="68f27-147">Отклик</span><span class="sxs-lookup"><span data-stu-id="68f27-147">Response</span></span>
<span data-ttu-id="68f27-148">При успешном и оповещении и на устройстве существует - 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="68f27-148">If successful and alert and device exist - 200 OK.</span></span> <span data-ttu-id="68f27-149">Если оповещение не найдено или устройство не найдено - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="68f27-149">If alert not found or device not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="68f27-150">Пример</span><span class="sxs-lookup"><span data-stu-id="68f27-150">Example</span></span>

<span data-ttu-id="68f27-151">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="68f27-151">**Request**</span></span>

<span data-ttu-id="68f27-152">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="68f27-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/machine
```

<span data-ttu-id="68f27-153">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="68f27-153">**Response**</span></span>

<span data-ttu-id="68f27-154">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="68f27-154">Here is an example of the response.</span></span>


```json
{
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2021-01-25T07:27:36.052313Z",
    "osPlatform": "Windows10",
    "osProcessor": "x64",
    "version": "1901",
    "lastIpAddress": "10.166.113.46",
    "lastExternalIpAddress": "167.220.203.175",
    "osBuild": 19042,
    "healthStatus": "Active",
    "deviceValue": "Normal",
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Low",
    "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
    "machineTags": [
        "Tag1",
        "Tag2"
    ],
    "ipAddresses": [
        {
            "ipAddress": "10.166.113.47",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        },
        {
            "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        }
    ]
}
```