---
title: Получать сведения об ИП, связанных с оповещением
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
ms.technology: mde
ms.openlocfilehash: 970f82038bd7feb4f0c568ed13b285f75bf1ab19
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167059"
---
# <a name="get-alert-related-ips-information-api"></a><span data-ttu-id="7cc71-104">Получить API сведений об ИП, связанных с оповещением</span><span class="sxs-lookup"><span data-stu-id="7cc71-104">Get alert related IPs information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7cc71-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7cc71-105">**Applies to:**</span></span>
- [<span data-ttu-id="7cc71-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7cc71-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7cc71-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7cc71-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7cc71-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7cc71-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7cc71-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7cc71-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="7cc71-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="7cc71-110">API description</span></span>
<span data-ttu-id="7cc71-111">Извлекает все IPs, связанные с определенным оповещением.</span><span class="sxs-lookup"><span data-stu-id="7cc71-111">Retrieves all IPs related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="7cc71-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="7cc71-112">Limitations</span></span>
1. <span data-ttu-id="7cc71-113">Вы можете запрашивать последние обновления оповещений в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="7cc71-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="7cc71-114">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="7cc71-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="7cc71-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="7cc71-115">Permissions</span></span>
<span data-ttu-id="7cc71-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="7cc71-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7cc71-117">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7cc71-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="7cc71-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="7cc71-118">Permission type</span></span> |   <span data-ttu-id="7cc71-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="7cc71-119">Permission</span></span>  |   <span data-ttu-id="7cc71-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="7cc71-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7cc71-121">Приложение</span><span class="sxs-lookup"><span data-stu-id="7cc71-121">Application</span></span> |   <span data-ttu-id="7cc71-122">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="7cc71-122">Ip.Read.All</span></span> |   <span data-ttu-id="7cc71-123">'Read IP address profiles'</span><span class="sxs-lookup"><span data-stu-id="7cc71-123">'Read IP address profiles'</span></span>
<span data-ttu-id="7cc71-124">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="7cc71-124">Delegated (work or school account)</span></span> | <span data-ttu-id="7cc71-125">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="7cc71-125">Ip.Read.All</span></span> |  <span data-ttu-id="7cc71-126">'Read IP address profiles'</span><span class="sxs-lookup"><span data-stu-id="7cc71-126">'Read IP address profiles'</span></span>

>[!Note]
> <span data-ttu-id="7cc71-127">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="7cc71-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="7cc71-128">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="7cc71-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="7cc71-129">Пользователь должен иметь доступ к устройству, связанному с оповещением, на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="7cc71-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="7cc71-130">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="7cc71-130">HTTP request</span></span>
```
GET /api/alerts/{id}/ips
```

## <a name="request-headers"></a><span data-ttu-id="7cc71-131">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="7cc71-131">Request headers</span></span>

<span data-ttu-id="7cc71-132">Имя</span><span class="sxs-lookup"><span data-stu-id="7cc71-132">Name</span></span> | <span data-ttu-id="7cc71-133">Тип</span><span class="sxs-lookup"><span data-stu-id="7cc71-133">Type</span></span> | <span data-ttu-id="7cc71-134">Описание</span><span class="sxs-lookup"><span data-stu-id="7cc71-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="7cc71-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="7cc71-135">Authorization</span></span> | <span data-ttu-id="7cc71-136">Строка</span><span class="sxs-lookup"><span data-stu-id="7cc71-136">String</span></span> | <span data-ttu-id="7cc71-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="7cc71-137">Bearer {token}.</span></span> <span data-ttu-id="7cc71-138">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="7cc71-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="7cc71-139">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="7cc71-139">Request body</span></span>
<span data-ttu-id="7cc71-140">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="7cc71-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="7cc71-141">Отклик</span><span class="sxs-lookup"><span data-stu-id="7cc71-141">Response</span></span>
<span data-ttu-id="7cc71-142">При успешном и оповещении и ip существует - 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="7cc71-142">If successful and alert and an IP exist - 200 OK.</span></span> <span data-ttu-id="7cc71-143">Если оповещение не найдено - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="7cc71-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="7cc71-144">Пример</span><span class="sxs-lookup"><span data-stu-id="7cc71-144">Example</span></span>

<span data-ttu-id="7cc71-145">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="7cc71-145">**Request**</span></span>

<span data-ttu-id="7cc71-146">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="7cc71-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/ips
```

<span data-ttu-id="7cc71-147">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="7cc71-147">**Response**</span></span>

<span data-ttu-id="7cc71-148">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="7cc71-148">Here is an example of the response.</span></span>


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
