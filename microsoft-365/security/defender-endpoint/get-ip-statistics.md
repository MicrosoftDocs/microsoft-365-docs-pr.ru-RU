---
title: Получить API статистики IP
description: Получите последнюю статистику для IP-адреса с помощью Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, ip, statistics, prevalence
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
ms.openlocfilehash: c47a5e58b1888447a4428fad78e71b85cfe79b69
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167184"
---
# <a name="get-ip-statistics-api"></a><span data-ttu-id="cafd5-104">Получить API статистики IP</span><span class="sxs-lookup"><span data-stu-id="cafd5-104">Get IP statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cafd5-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="cafd5-105">**Applies to:**</span></span>
- [<span data-ttu-id="cafd5-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="cafd5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cafd5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cafd5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cafd5-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="cafd5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cafd5-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="cafd5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="cafd5-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="cafd5-110">API description</span></span>
<span data-ttu-id="cafd5-111">Извлекает статистику для данного IP- адреса.</span><span class="sxs-lookup"><span data-stu-id="cafd5-111">Retrieves the statistics for the given IP.</span></span>

## <a name="limitations"></a><span data-ttu-id="cafd5-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="cafd5-112">Limitations</span></span>
1. <span data-ttu-id="cafd5-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="cafd5-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="cafd5-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="cafd5-114">Permissions</span></span>
<span data-ttu-id="cafd5-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="cafd5-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cafd5-116">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cafd5-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="cafd5-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="cafd5-117">Permission type</span></span> |   <span data-ttu-id="cafd5-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="cafd5-118">Permission</span></span>  |   <span data-ttu-id="cafd5-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="cafd5-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cafd5-120">Приложение</span><span class="sxs-lookup"><span data-stu-id="cafd5-120">Application</span></span> |   <span data-ttu-id="cafd5-121">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="cafd5-121">Ip.Read.All</span></span> |   <span data-ttu-id="cafd5-122">'Read IP address profiles'</span><span class="sxs-lookup"><span data-stu-id="cafd5-122">'Read IP address profiles'</span></span>
<span data-ttu-id="cafd5-123">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="cafd5-123">Delegated (work or school account)</span></span> | <span data-ttu-id="cafd5-124">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="cafd5-124">Ip.Read.All</span></span> |  <span data-ttu-id="cafd5-125">'Read IP address profiles'</span><span class="sxs-lookup"><span data-stu-id="cafd5-125">'Read IP address profiles'</span></span>

>[!NOTE]
> <span data-ttu-id="cafd5-126">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="cafd5-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="cafd5-127">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="cafd5-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="cafd5-128">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="cafd5-128">HTTP request</span></span>

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a><span data-ttu-id="cafd5-129">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="cafd5-129">Request headers</span></span>

<span data-ttu-id="cafd5-130">Имя</span><span class="sxs-lookup"><span data-stu-id="cafd5-130">Name</span></span> | <span data-ttu-id="cafd5-131">Тип</span><span class="sxs-lookup"><span data-stu-id="cafd5-131">Type</span></span> | <span data-ttu-id="cafd5-132">Описание</span><span class="sxs-lookup"><span data-stu-id="cafd5-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="cafd5-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="cafd5-133">Authorization</span></span> | <span data-ttu-id="cafd5-134">Строка</span><span class="sxs-lookup"><span data-stu-id="cafd5-134">String</span></span> | <span data-ttu-id="cafd5-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="cafd5-135">Bearer {token}.</span></span> <span data-ttu-id="cafd5-136">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="cafd5-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="cafd5-137">Запрос параметров URI</span><span class="sxs-lookup"><span data-stu-id="cafd5-137">Request URI parameters</span></span>

<span data-ttu-id="cafd5-138">Имя</span><span class="sxs-lookup"><span data-stu-id="cafd5-138">Name</span></span> | <span data-ttu-id="cafd5-139">Тип</span><span class="sxs-lookup"><span data-stu-id="cafd5-139">Type</span></span> | <span data-ttu-id="cafd5-140">Описание</span><span class="sxs-lookup"><span data-stu-id="cafd5-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="cafd5-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="cafd5-141">lookBackHours</span></span> | <span data-ttu-id="cafd5-142">Int32</span><span class="sxs-lookup"><span data-stu-id="cafd5-142">Int32</span></span> | <span data-ttu-id="cafd5-143">Определяет часы поиска, чтобы получить статистику.</span><span class="sxs-lookup"><span data-stu-id="cafd5-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="cafd5-144">По умолчанию до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="cafd5-144">Defaults to 30 days.</span></span> <span data-ttu-id="cafd5-145">**Необязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="cafd5-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="cafd5-146">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="cafd5-146">Request body</span></span>
<span data-ttu-id="cafd5-147">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="cafd5-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cafd5-148">Отклик</span><span class="sxs-lookup"><span data-stu-id="cafd5-148">Response</span></span>
<span data-ttu-id="cafd5-149">При успешном и ip существует - 200 ОК со статистическими данными в теле.</span><span class="sxs-lookup"><span data-stu-id="cafd5-149">If successful and ip exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="cafd5-150">IP не существует - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="cafd5-150">IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="cafd5-151">Пример</span><span class="sxs-lookup"><span data-stu-id="cafd5-151">Example</span></span>

<span data-ttu-id="cafd5-152">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="cafd5-152">**Request**</span></span>

<span data-ttu-id="cafd5-153">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="cafd5-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

<span data-ttu-id="cafd5-154">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="cafd5-154">**Response**</span></span>

<span data-ttu-id="cafd5-155">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="cafd5-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "orgPrevalence": "63515",
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| <span data-ttu-id="cafd5-156">Имя</span><span class="sxs-lookup"><span data-stu-id="cafd5-156">Name</span></span> | <span data-ttu-id="cafd5-157">Описание</span><span class="sxs-lookup"><span data-stu-id="cafd5-157">Description</span></span> |
| :--- | :---------- |
| <span data-ttu-id="cafd5-158">Распространенность орг</span><span class="sxs-lookup"><span data-stu-id="cafd5-158">Org prevalence</span></span> | <span data-ttu-id="cafd5-159">отчетливое количество устройств, открывав сетевое подключение к этому IP.</span><span class="sxs-lookup"><span data-stu-id="cafd5-159">the distinct count of devices that opened network connection to this IP.</span></span> |
| <span data-ttu-id="cafd5-160">Первое увидено в Org</span><span class="sxs-lookup"><span data-stu-id="cafd5-160">Org first seen</span></span> | <span data-ttu-id="cafd5-161">первое подключение для этого IP-адреса в организации.</span><span class="sxs-lookup"><span data-stu-id="cafd5-161">the first connection for this IP in the organization.</span></span> |
| <span data-ttu-id="cafd5-162">Org последний раз видели</span><span class="sxs-lookup"><span data-stu-id="cafd5-162">Org last seen</span></span>  | <span data-ttu-id="cafd5-163">последнее подключение для этого IP-адреса в организации.</span><span class="sxs-lookup"><span data-stu-id="cafd5-163">the last connection for this IP in the organization.</span></span> |

> [!NOTE]
> <span data-ttu-id="cafd5-164">Эта статистика основана на данных за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="cafd5-164">This statistic information is based on data from the past 30 days.</span></span> 
