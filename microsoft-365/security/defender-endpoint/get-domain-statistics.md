---
title: Получить API статистики домена
description: Узнайте, как использовать API статистики домена Get для получения статистических данных на заданном домене в Microsoft Defender for Endpoint.
keywords: apis, graph api, supported apis, get, domain, domain related devices
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
ms.openlocfilehash: 50b05b98ba507e120bbd6a3dc09f4633dac3a005
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998780"
---
# <a name="get-domain-statistics-api"></a><span data-ttu-id="75239-104">Получить API статистики домена</span><span class="sxs-lookup"><span data-stu-id="75239-104">Get domain statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="75239-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="75239-105">**Applies to:**</span></span>
- [<span data-ttu-id="75239-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="75239-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="75239-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75239-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="75239-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="75239-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="75239-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="75239-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="75239-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="75239-110">API description</span></span>
<span data-ttu-id="75239-111">Извлекает статистику в заданном домене.</span><span class="sxs-lookup"><span data-stu-id="75239-111">Retrieves the statistics on the given domain.</span></span>


## <a name="limitations"></a><span data-ttu-id="75239-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="75239-112">Limitations</span></span>
1. <span data-ttu-id="75239-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="75239-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="75239-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="75239-114">Permissions</span></span>
<span data-ttu-id="75239-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="75239-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="75239-116">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="75239-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="75239-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="75239-117">Permission type</span></span> |   <span data-ttu-id="75239-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="75239-118">Permission</span></span>  |   <span data-ttu-id="75239-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="75239-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="75239-120">Приложение</span><span class="sxs-lookup"><span data-stu-id="75239-120">Application</span></span> |   <span data-ttu-id="75239-121">URL-адрес. Read.All</span><span class="sxs-lookup"><span data-stu-id="75239-121">URL.Read.All</span></span> |  <span data-ttu-id="75239-122">"Чтение URL-адресов"</span><span class="sxs-lookup"><span data-stu-id="75239-122">'Read URLs'</span></span>
<span data-ttu-id="75239-123">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="75239-123">Delegated (work or school account)</span></span> | <span data-ttu-id="75239-124">URL-адрес. Read.All</span><span class="sxs-lookup"><span data-stu-id="75239-124">URL.Read.All</span></span> | <span data-ttu-id="75239-125">"Чтение URL-адресов"</span><span class="sxs-lookup"><span data-stu-id="75239-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="75239-126">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="75239-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="75239-127">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="75239-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="75239-128">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="75239-128">HTTP request</span></span>
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a><span data-ttu-id="75239-129">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="75239-129">Request headers</span></span>

<span data-ttu-id="75239-130">Заголовок</span><span class="sxs-lookup"><span data-stu-id="75239-130">Header</span></span> | <span data-ttu-id="75239-131">Значение</span><span class="sxs-lookup"><span data-stu-id="75239-131">Value</span></span> 
:---|:---
<span data-ttu-id="75239-132">Авторизация</span><span class="sxs-lookup"><span data-stu-id="75239-132">Authorization</span></span> | <span data-ttu-id="75239-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="75239-133">Bearer {token}.</span></span> <span data-ttu-id="75239-134">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="75239-134">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="75239-135">Запрос параметров URI</span><span class="sxs-lookup"><span data-stu-id="75239-135">Request URI parameters</span></span>

<span data-ttu-id="75239-136">Имя</span><span class="sxs-lookup"><span data-stu-id="75239-136">Name</span></span> | <span data-ttu-id="75239-137">Тип</span><span class="sxs-lookup"><span data-stu-id="75239-137">Type</span></span> | <span data-ttu-id="75239-138">Описание</span><span class="sxs-lookup"><span data-stu-id="75239-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="75239-139">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="75239-139">lookBackHours</span></span> | <span data-ttu-id="75239-140">Int32</span><span class="sxs-lookup"><span data-stu-id="75239-140">Int32</span></span> | <span data-ttu-id="75239-141">Определяет часы поиска, чтобы получить статистику.</span><span class="sxs-lookup"><span data-stu-id="75239-141">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="75239-142">По умолчанию до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="75239-142">Defaults to 30 days.</span></span> <span data-ttu-id="75239-143">**Необязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="75239-143">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="75239-144">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="75239-144">Request body</span></span>
<span data-ttu-id="75239-145">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="75239-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="75239-146">Отклик</span><span class="sxs-lookup"><span data-stu-id="75239-146">Response</span></span>
<span data-ttu-id="75239-147">При успешном и домене существует — 200 ОК, с объектом статистики в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="75239-147">If successful and domain exists - 200 OK, with statistics object in the response body.</span></span> <span data-ttu-id="75239-148">Если домена не существует - 404 Не найден.</span><span class="sxs-lookup"><span data-stu-id="75239-148">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="75239-149">Пример</span><span class="sxs-lookup"><span data-stu-id="75239-149">Example</span></span>

<span data-ttu-id="75239-150">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="75239-150">**Request**</span></span>

<span data-ttu-id="75239-151">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="75239-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

<span data-ttu-id="75239-152">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="75239-152">**Response**</span></span>

<span data-ttu-id="75239-153">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="75239-153">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "organizationPrevalence": 4070,
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
