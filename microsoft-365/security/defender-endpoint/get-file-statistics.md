---
title: Получить API статистики файлов
description: Узнайте, как использовать API статистики файлов Get для получения статистики для данного файла в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, file, statistics
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
ms.openlocfilehash: 826b2ff25363f1d9a6276e1a42a10c1cf4995904
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998816"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="1af8e-104">Получить API статистики файлов</span><span class="sxs-lookup"><span data-stu-id="1af8e-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1af8e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1af8e-105">**Applies to:**</span></span>
- [<span data-ttu-id="1af8e-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1af8e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1af8e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1af8e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1af8e-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1af8e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1af8e-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1af8e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="1af8e-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="1af8e-110">API description</span></span>
<span data-ttu-id="1af8e-111">Извлекает статистику для данного файла.</span><span class="sxs-lookup"><span data-stu-id="1af8e-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="1af8e-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1af8e-112">Limitations</span></span>
1. <span data-ttu-id="1af8e-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="1af8e-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1af8e-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="1af8e-114">Permissions</span></span>
<span data-ttu-id="1af8e-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="1af8e-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1af8e-116">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1af8e-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1af8e-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="1af8e-117">Permission type</span></span> |   <span data-ttu-id="1af8e-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="1af8e-118">Permission</span></span>  |   <span data-ttu-id="1af8e-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="1af8e-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1af8e-120">Приложение</span><span class="sxs-lookup"><span data-stu-id="1af8e-120">Application</span></span> |   <span data-ttu-id="1af8e-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="1af8e-121">File.Read.All</span></span> | <span data-ttu-id="1af8e-122">'Read file profiles'</span><span class="sxs-lookup"><span data-stu-id="1af8e-122">'Read file profiles'</span></span>
<span data-ttu-id="1af8e-123">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="1af8e-123">Delegated (work or school account)</span></span> | <span data-ttu-id="1af8e-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="1af8e-124">File.Read.All</span></span> | <span data-ttu-id="1af8e-125">'Read file profiles'</span><span class="sxs-lookup"><span data-stu-id="1af8e-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="1af8e-126">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="1af8e-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="1af8e-127">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="1af8e-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1af8e-128">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="1af8e-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="1af8e-129">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="1af8e-129">Request headers</span></span>

<span data-ttu-id="1af8e-130">Имя</span><span class="sxs-lookup"><span data-stu-id="1af8e-130">Name</span></span> | <span data-ttu-id="1af8e-131">Тип</span><span class="sxs-lookup"><span data-stu-id="1af8e-131">Type</span></span> | <span data-ttu-id="1af8e-132">Описание</span><span class="sxs-lookup"><span data-stu-id="1af8e-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="1af8e-133">Авторизация</span><span class="sxs-lookup"><span data-stu-id="1af8e-133">Authorization</span></span> | <span data-ttu-id="1af8e-134">String</span><span class="sxs-lookup"><span data-stu-id="1af8e-134">String</span></span> | <span data-ttu-id="1af8e-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1af8e-135">Bearer {token}.</span></span> <span data-ttu-id="1af8e-136">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="1af8e-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="1af8e-137">Запрос параметров URI</span><span class="sxs-lookup"><span data-stu-id="1af8e-137">Request URI parameters</span></span>

<span data-ttu-id="1af8e-138">Имя</span><span class="sxs-lookup"><span data-stu-id="1af8e-138">Name</span></span> | <span data-ttu-id="1af8e-139">Тип</span><span class="sxs-lookup"><span data-stu-id="1af8e-139">Type</span></span> | <span data-ttu-id="1af8e-140">Описание</span><span class="sxs-lookup"><span data-stu-id="1af8e-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="1af8e-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="1af8e-141">lookBackHours</span></span> | <span data-ttu-id="1af8e-142">Int32</span><span class="sxs-lookup"><span data-stu-id="1af8e-142">Int32</span></span> | <span data-ttu-id="1af8e-143">Определяет часы поиска, чтобы получить статистику.</span><span class="sxs-lookup"><span data-stu-id="1af8e-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="1af8e-144">По умолчанию до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="1af8e-144">Defaults to 30 days.</span></span> <span data-ttu-id="1af8e-145">**Необязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="1af8e-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="1af8e-146">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="1af8e-146">Request body</span></span>
<span data-ttu-id="1af8e-147">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="1af8e-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1af8e-148">Отклик</span><span class="sxs-lookup"><span data-stu-id="1af8e-148">Response</span></span>
<span data-ttu-id="1af8e-149">Если успешно и файл существует — 200 ОК со статистическими данными в теле.</span><span class="sxs-lookup"><span data-stu-id="1af8e-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="1af8e-150">Если файл не существует - 404 Не найден.</span><span class="sxs-lookup"><span data-stu-id="1af8e-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="1af8e-151">Пример</span><span class="sxs-lookup"><span data-stu-id="1af8e-151">Example</span></span>

<span data-ttu-id="1af8e-152">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="1af8e-152">**Request**</span></span>

<span data-ttu-id="1af8e-153">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="1af8e-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="1af8e-154">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="1af8e-154">**Response**</span></span>

<span data-ttu-id="1af8e-155">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="1af8e-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "organizationPrevalence": 14850,
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globallyPrevalence": 705012,
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```
