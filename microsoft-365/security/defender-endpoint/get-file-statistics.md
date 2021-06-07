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
ms.openlocfilehash: 6063d29562be40aed3060e241b52b1a2936aa36d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770209"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="632b4-104">Получить API статистики файлов</span><span class="sxs-lookup"><span data-stu-id="632b4-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="632b4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="632b4-105">**Applies to:**</span></span>
- [<span data-ttu-id="632b4-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="632b4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="632b4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="632b4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="632b4-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="632b4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="632b4-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="632b4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="632b4-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="632b4-110">API description</span></span>
<span data-ttu-id="632b4-111">Извлекает статистику для данного файла.</span><span class="sxs-lookup"><span data-stu-id="632b4-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="632b4-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="632b4-112">Limitations</span></span>
1. <span data-ttu-id="632b4-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="632b4-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="632b4-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="632b4-114">Permissions</span></span>
<span data-ttu-id="632b4-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="632b4-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="632b4-116">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="632b4-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="632b4-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="632b4-117">Permission type</span></span> |   <span data-ttu-id="632b4-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="632b4-118">Permission</span></span>  |   <span data-ttu-id="632b4-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="632b4-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="632b4-120">Приложение</span><span class="sxs-lookup"><span data-stu-id="632b4-120">Application</span></span> |   <span data-ttu-id="632b4-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="632b4-121">File.Read.All</span></span> | <span data-ttu-id="632b4-122">'Read file profiles'</span><span class="sxs-lookup"><span data-stu-id="632b4-122">'Read file profiles'</span></span>
<span data-ttu-id="632b4-123">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="632b4-123">Delegated (work or school account)</span></span> | <span data-ttu-id="632b4-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="632b4-124">File.Read.All</span></span> | <span data-ttu-id="632b4-125">'Read file profiles'</span><span class="sxs-lookup"><span data-stu-id="632b4-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="632b4-126">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="632b4-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="632b4-127">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="632b4-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="632b4-128">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="632b4-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="632b4-129">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="632b4-129">Request headers</span></span>

<span data-ttu-id="632b4-130">Имя</span><span class="sxs-lookup"><span data-stu-id="632b4-130">Name</span></span> | <span data-ttu-id="632b4-131">Тип</span><span class="sxs-lookup"><span data-stu-id="632b4-131">Type</span></span> | <span data-ttu-id="632b4-132">Описание</span><span class="sxs-lookup"><span data-stu-id="632b4-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="632b4-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="632b4-133">Authorization</span></span> | <span data-ttu-id="632b4-134">String</span><span class="sxs-lookup"><span data-stu-id="632b4-134">String</span></span> | <span data-ttu-id="632b4-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="632b4-135">Bearer {token}.</span></span> <span data-ttu-id="632b4-136">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="632b4-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="632b4-137">Запрос параметров URI</span><span class="sxs-lookup"><span data-stu-id="632b4-137">Request URI parameters</span></span>

<span data-ttu-id="632b4-138">Имя</span><span class="sxs-lookup"><span data-stu-id="632b4-138">Name</span></span> | <span data-ttu-id="632b4-139">Тип</span><span class="sxs-lookup"><span data-stu-id="632b4-139">Type</span></span> | <span data-ttu-id="632b4-140">Описание</span><span class="sxs-lookup"><span data-stu-id="632b4-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="632b4-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="632b4-141">lookBackHours</span></span> | <span data-ttu-id="632b4-142">Int32</span><span class="sxs-lookup"><span data-stu-id="632b4-142">Int32</span></span> | <span data-ttu-id="632b4-143">Определяет часы поиска, чтобы получить статистику.</span><span class="sxs-lookup"><span data-stu-id="632b4-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="632b4-144">По умолчанию до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="632b4-144">Defaults to 30 days.</span></span> <span data-ttu-id="632b4-145">**Необязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="632b4-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="632b4-146">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="632b4-146">Request body</span></span>
<span data-ttu-id="632b4-147">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="632b4-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="632b4-148">Отклик</span><span class="sxs-lookup"><span data-stu-id="632b4-148">Response</span></span>
<span data-ttu-id="632b4-149">Если успешно и файл существует — 200 ОК со статистическими данными в теле.</span><span class="sxs-lookup"><span data-stu-id="632b4-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="632b4-150">Если файл не существует - 404 Не найден.</span><span class="sxs-lookup"><span data-stu-id="632b4-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="632b4-151">Пример</span><span class="sxs-lookup"><span data-stu-id="632b4-151">Example</span></span>

<span data-ttu-id="632b4-152">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="632b4-152">**Request**</span></span>

<span data-ttu-id="632b4-153">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="632b4-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="632b4-154">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="632b4-154">**Response**</span></span>

<span data-ttu-id="632b4-155">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="632b4-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "orgPrevalence": "14850",
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globalPrevalence": "705012",
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```
