---
title: Получить API объекта MachineAction
description: Узнайте, как использовать API Get MachineAction для получения определенного действия машины по его ID в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, machineaction object
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
ms.openlocfilehash: 180179d5b1362ad4952618148b11007aa9efe91c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200069"
---
# <a name="get-machineaction-api"></a><span data-ttu-id="1d5c7-104">Получите API machineAction</span><span class="sxs-lookup"><span data-stu-id="1d5c7-104">Get machineAction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1d5c7-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1d5c7-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1d5c7-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1d5c7-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1d5c7-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1d5c7-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="1d5c7-108">Описание API</span><span class="sxs-lookup"><span data-stu-id="1d5c7-108">API description</span></span>
<span data-ttu-id="1d5c7-109">Извлекает [определенное действие машины](machineaction.md) по его ID.</span><span class="sxs-lookup"><span data-stu-id="1d5c7-109">Retrieves specific [Machine Action](machineaction.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="1d5c7-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1d5c7-110">Limitations</span></span>
1. <span data-ttu-id="1d5c7-111">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="1d5c7-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1d5c7-112">Разрешения</span><span class="sxs-lookup"><span data-stu-id="1d5c7-112">Permissions</span></span>
<span data-ttu-id="1d5c7-113">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="1d5c7-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1d5c7-114">Дополнительные новости, в том числе выбор разрешений, см. в этой [ссылке: Use Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1d5c7-114">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1d5c7-115">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="1d5c7-115">Permission type</span></span> |   <span data-ttu-id="1d5c7-116">Разрешение</span><span class="sxs-lookup"><span data-stu-id="1d5c7-116">Permission</span></span>  |   <span data-ttu-id="1d5c7-117">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="1d5c7-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1d5c7-118">Application</span><span class="sxs-lookup"><span data-stu-id="1d5c7-118">Application</span></span> |   <span data-ttu-id="1d5c7-119">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="1d5c7-119">Machine.Read.All</span></span> |  <span data-ttu-id="1d5c7-120">'Read all machine profiles'</span><span class="sxs-lookup"><span data-stu-id="1d5c7-120">'Read all machine profiles'</span></span>
<span data-ttu-id="1d5c7-121">Application</span><span class="sxs-lookup"><span data-stu-id="1d5c7-121">Application</span></span> |   <span data-ttu-id="1d5c7-122">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="1d5c7-122">Machine.ReadWrite.All</span></span> | <span data-ttu-id="1d5c7-123">'Read and write all machine information'</span><span class="sxs-lookup"><span data-stu-id="1d5c7-123">'Read and write all machine information'</span></span>
<span data-ttu-id="1d5c7-124">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="1d5c7-124">Delegated (work or school account)</span></span> | <span data-ttu-id="1d5c7-125">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="1d5c7-125">Machine.Read</span></span> | <span data-ttu-id="1d5c7-126">'Read machine information'</span><span class="sxs-lookup"><span data-stu-id="1d5c7-126">'Read machine information'</span></span>
<span data-ttu-id="1d5c7-127">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="1d5c7-127">Delegated (work or school account)</span></span> | <span data-ttu-id="1d5c7-128">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1d5c7-128">Machine.ReadWrite</span></span> | <span data-ttu-id="1d5c7-129">'Read and write machine information'</span><span class="sxs-lookup"><span data-stu-id="1d5c7-129">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="1d5c7-130">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="1d5c7-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="1d5c7-131">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="1d5c7-131">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1d5c7-132">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="1d5c7-132">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions/{id}
```

## <a name="request-headers"></a><span data-ttu-id="1d5c7-133">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="1d5c7-133">Request headers</span></span>

<span data-ttu-id="1d5c7-134">Имя</span><span class="sxs-lookup"><span data-stu-id="1d5c7-134">Name</span></span> | <span data-ttu-id="1d5c7-135">Тип</span><span class="sxs-lookup"><span data-stu-id="1d5c7-135">Type</span></span> | <span data-ttu-id="1d5c7-136">Описание</span><span class="sxs-lookup"><span data-stu-id="1d5c7-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="1d5c7-137">Авторизация</span><span class="sxs-lookup"><span data-stu-id="1d5c7-137">Authorization</span></span> | <span data-ttu-id="1d5c7-138">Строка</span><span class="sxs-lookup"><span data-stu-id="1d5c7-138">String</span></span> | <span data-ttu-id="1d5c7-139">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1d5c7-139">Bearer {token}.</span></span> <span data-ttu-id="1d5c7-140">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="1d5c7-140">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1d5c7-141">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="1d5c7-141">Request body</span></span>
<span data-ttu-id="1d5c7-142">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="1d5c7-142">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1d5c7-143">Отклик</span><span class="sxs-lookup"><span data-stu-id="1d5c7-143">Response</span></span>
<span data-ttu-id="1d5c7-144">В случае успешной работы этот метод возвращает код ответа 200 Ok с [объектом Machine Action.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="1d5c7-144">If successful, this method returns 200, Ok response code with a [Machine Action](machineaction.md) entity.</span></span> <span data-ttu-id="1d5c7-145">Если объект действия машины с указанным id не найден - 404 Не найден.</span><span class="sxs-lookup"><span data-stu-id="1d5c7-145">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="1d5c7-146">Пример</span><span class="sxs-lookup"><span data-stu-id="1d5c7-146">Example</span></span>

<span data-ttu-id="1d5c7-147">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="1d5c7-147">**Request**</span></span>

<span data-ttu-id="1d5c7-148">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="1d5c7-148">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions/2e9da30d-27f6-4208-81f2-9cd3d67893ba
```

<span data-ttu-id="1d5c7-149">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="1d5c7-149">**Response**</span></span>

<span data-ttu-id="1d5c7-150">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="1d5c7-150">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
    "type": "Isolate",
    "scope": "Selective",
    "requestor": "Analyst@TestPrd.onmicrosoft.com",
    "requestorComment": "test for docs",
    "status": "Succeeded",
    "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
    "computerDnsName": "desktop-test",
    "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
    "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
    "relatedFileInfo": null
}


```
