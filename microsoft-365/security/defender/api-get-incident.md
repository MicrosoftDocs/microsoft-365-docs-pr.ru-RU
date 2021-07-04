---
title: Получить API инцидентов
description: Узнайте, как использовать API get incidents для получения одного инцидента в Microsoft 365 Defender.
keywords: apis, graph api, supported apis, get, file, hash
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
ms.openlocfilehash: 2e051803a4cd228e3b455ec08b30e5c2197ca9a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289611"
---
# <a name="get-incident-information-api"></a><span data-ttu-id="28a85-104">Получить API сведений об инцидентах</span><span class="sxs-lookup"><span data-stu-id="28a85-104">Get incident information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="28a85-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="28a85-105">**Applies to:**</span></span>
- [<span data-ttu-id="28a85-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28a85-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="28a85-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="28a85-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="28a85-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="28a85-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="28a85-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="28a85-109">API description</span></span>

<span data-ttu-id="28a85-110">Извлечение определенного инцидента по его ID</span><span class="sxs-lookup"><span data-stu-id="28a85-110">Retrieves a specific incident by its ID</span></span>

## <a name="limitations"></a><span data-ttu-id="28a85-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="28a85-111">Limitations</span></span>

1. <span data-ttu-id="28a85-112">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="28a85-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="28a85-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="28a85-113">Permissions</span></span>

<span data-ttu-id="28a85-114">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="28a85-114">One of the following permissions is required to call this API.</span></span> 

<span data-ttu-id="28a85-115">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="28a85-115">Permission type</span></span> | <span data-ttu-id="28a85-116">Разрешение</span><span class="sxs-lookup"><span data-stu-id="28a85-116">Permission</span></span> | <span data-ttu-id="28a85-117">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="28a85-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="28a85-118">Application</span><span class="sxs-lookup"><span data-stu-id="28a85-118">Application</span></span> | <span data-ttu-id="28a85-119">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="28a85-119">Incident.Read.All</span></span> | <span data-ttu-id="28a85-120">'Read all Incidents'</span><span class="sxs-lookup"><span data-stu-id="28a85-120">'Read all Incidents'</span></span>
<span data-ttu-id="28a85-121">Application</span><span class="sxs-lookup"><span data-stu-id="28a85-121">Application</span></span> | <span data-ttu-id="28a85-122">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="28a85-122">Incident.ReadWrite.All</span></span> | <span data-ttu-id="28a85-123">'Read and write all Incidents'</span><span class="sxs-lookup"><span data-stu-id="28a85-123">'Read and write all Incidents'</span></span>
<span data-ttu-id="28a85-124">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="28a85-124">Delegated (work or school account)</span></span> | <span data-ttu-id="28a85-125">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="28a85-125">Incident.Read</span></span> | <span data-ttu-id="28a85-126">'Read Incidents'</span><span class="sxs-lookup"><span data-stu-id="28a85-126">'Read Incidents'</span></span>
<span data-ttu-id="28a85-127">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="28a85-127">Delegated (work or school account)</span></span> | <span data-ttu-id="28a85-128">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="28a85-128">Incident.ReadWrite</span></span> | <span data-ttu-id="28a85-129">'Read and write Incidents'</span><span class="sxs-lookup"><span data-stu-id="28a85-129">'Read and write Incidents'</span></span>

> [!NOTE]
>
> <span data-ttu-id="28a85-130">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="28a85-130">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="28a85-131">У пользователя должно быть по крайней мере следующее разрешение на роль: "Просмотр данных"</span><span class="sxs-lookup"><span data-stu-id="28a85-131">The user needs to have at least the following role permission: 'View Data'</span></span>
> - <span data-ttu-id="28a85-132">Ответ будет включать только инциденты, которые пользователь подвергается воздействию</span><span class="sxs-lookup"><span data-stu-id="28a85-132">The response will only include incidents that the user is exposed to</span></span>

## <a name="http-request"></a><span data-ttu-id="28a85-133">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="28a85-133">HTTP request</span></span>

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a><span data-ttu-id="28a85-134">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="28a85-134">Request headers</span></span>

<span data-ttu-id="28a85-135">Имя</span><span class="sxs-lookup"><span data-stu-id="28a85-135">Name</span></span> | <span data-ttu-id="28a85-136">Тип</span><span class="sxs-lookup"><span data-stu-id="28a85-136">Type</span></span> | <span data-ttu-id="28a85-137">Описание</span><span class="sxs-lookup"><span data-stu-id="28a85-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="28a85-138">Authorization</span><span class="sxs-lookup"><span data-stu-id="28a85-138">Authorization</span></span> | <span data-ttu-id="28a85-139">Строка</span><span class="sxs-lookup"><span data-stu-id="28a85-139">String</span></span> | <span data-ttu-id="28a85-140">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="28a85-140">Bearer {token}.</span></span> <span data-ttu-id="28a85-141">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="28a85-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="28a85-142">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="28a85-142">Request body</span></span>

<span data-ttu-id="28a85-143">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="28a85-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="28a85-144">Отклик</span><span class="sxs-lookup"><span data-stu-id="28a85-144">Response</span></span>

<span data-ttu-id="28a85-145">В случае успешной работы этот метод возвращает 200 ОК и объект инцидента в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="28a85-145">If successful, this method returns 200 OK, and the incident entity in the response body.</span></span> <span data-ttu-id="28a85-146">Если инцидент с указанным id не найден - 404 Не найден.</span><span class="sxs-lookup"><span data-stu-id="28a85-146">If incident with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="28a85-147">Пример</span><span class="sxs-lookup"><span data-stu-id="28a85-147">Example</span></span>

<span data-ttu-id="28a85-148">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="28a85-148">**Request**</span></span>

<span data-ttu-id="28a85-149">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="28a85-149">Here is an example of the request.</span></span>

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
