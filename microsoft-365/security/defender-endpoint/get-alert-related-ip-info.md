---
title: Получить сведения о связанных с оповещением IP
description: Извлечение всех IPs, связанных с определенным оповещением с помощью Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get alert information, alert information, related ip
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b6ac9746ff82f81772505daac7d7f36249687d7d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772333"
---
# <a name="get-alert-related-ips-information-api"></a><span data-ttu-id="3cd35-104">Получить API сведений об ИП, связанных с оповещением</span><span class="sxs-lookup"><span data-stu-id="3cd35-104">Get alert related IPs information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3cd35-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3cd35-105">**Applies to:**</span></span>
- [<span data-ttu-id="3cd35-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3cd35-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3cd35-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cd35-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3cd35-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="3cd35-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3cd35-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="3cd35-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3cd35-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="3cd35-110">API description</span></span>
<span data-ttu-id="3cd35-111">Извлекает все IPs, связанные с определенным оповещением.</span><span class="sxs-lookup"><span data-stu-id="3cd35-111">Retrieves all IPs related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="3cd35-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="3cd35-112">Limitations</span></span>
1. <span data-ttu-id="3cd35-113">Вы можете запрашивать последние обновления оповещений в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="3cd35-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="3cd35-114">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="3cd35-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3cd35-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="3cd35-115">Permissions</span></span>
<span data-ttu-id="3cd35-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="3cd35-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3cd35-117">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3cd35-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3cd35-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="3cd35-118">Permission type</span></span> |   <span data-ttu-id="3cd35-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="3cd35-119">Permission</span></span>  |   <span data-ttu-id="3cd35-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="3cd35-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3cd35-121">Приложение</span><span class="sxs-lookup"><span data-stu-id="3cd35-121">Application</span></span> |   <span data-ttu-id="3cd35-122">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="3cd35-122">Ip.Read.All</span></span> |   <span data-ttu-id="3cd35-123">'Read IP address profiles'</span><span class="sxs-lookup"><span data-stu-id="3cd35-123">'Read IP address profiles'</span></span>
<span data-ttu-id="3cd35-124">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="3cd35-124">Delegated (work or school account)</span></span> | <span data-ttu-id="3cd35-125">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="3cd35-125">Ip.Read.All</span></span> |  <span data-ttu-id="3cd35-126">'Read IP address profiles'</span><span class="sxs-lookup"><span data-stu-id="3cd35-126">'Read IP address profiles'</span></span>

>[!Note]
> <span data-ttu-id="3cd35-127">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="3cd35-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3cd35-128">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="3cd35-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="3cd35-129">Пользователь должен иметь доступ к устройству, связанному с оповещением, на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="3cd35-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3cd35-130">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="3cd35-130">HTTP request</span></span>
```
GET /api/alerts/{id}/ips
```

## <a name="request-headers"></a><span data-ttu-id="3cd35-131">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="3cd35-131">Request headers</span></span>

<span data-ttu-id="3cd35-132">Имя</span><span class="sxs-lookup"><span data-stu-id="3cd35-132">Name</span></span> | <span data-ttu-id="3cd35-133">Тип</span><span class="sxs-lookup"><span data-stu-id="3cd35-133">Type</span></span> | <span data-ttu-id="3cd35-134">Описание</span><span class="sxs-lookup"><span data-stu-id="3cd35-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="3cd35-135">Авторизация</span><span class="sxs-lookup"><span data-stu-id="3cd35-135">Authorization</span></span> | <span data-ttu-id="3cd35-136">String</span><span class="sxs-lookup"><span data-stu-id="3cd35-136">String</span></span> | <span data-ttu-id="3cd35-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="3cd35-137">Bearer {token}.</span></span> <span data-ttu-id="3cd35-138">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="3cd35-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3cd35-139">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="3cd35-139">Request body</span></span>
<span data-ttu-id="3cd35-140">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="3cd35-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3cd35-141">Отклик</span><span class="sxs-lookup"><span data-stu-id="3cd35-141">Response</span></span>
<span data-ttu-id="3cd35-142">При успешном и оповещении и ip существует - 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="3cd35-142">If successful and alert and an IP exist - 200 OK.</span></span> <span data-ttu-id="3cd35-143">Если оповещение не найдено - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="3cd35-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3cd35-144">Пример</span><span class="sxs-lookup"><span data-stu-id="3cd35-144">Example</span></span>

<span data-ttu-id="3cd35-145">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="3cd35-145">**Request**</span></span>

<span data-ttu-id="3cd35-146">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="3cd35-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/ips
```

<span data-ttu-id="3cd35-147">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="3cd35-147">**Response**</span></span>

<span data-ttu-id="3cd35-148">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="3cd35-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Ips",    
    "value": [
                {
                    "id": "104.80.104.128"
                },
                {
                    "id": "23.203.232.228   
                }
                ...
    ]
}
 
```
