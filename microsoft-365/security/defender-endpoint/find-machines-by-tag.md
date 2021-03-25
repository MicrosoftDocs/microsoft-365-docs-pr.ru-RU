---
title: Поиск устройств по тегу API
description: Поиск всех устройств, содержащих тег specifc
keywords: apis, поддерживаемые apis, get, device, find, find device, by tag, tag
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
ms.openlocfilehash: 6460860828acd5ea0c3509e9eb06061d2a9a0cc2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200153"
---
# <a name="find-devices-by-tag-api"></a><span data-ttu-id="86988-104">Поиск устройств по тегу API</span><span class="sxs-lookup"><span data-stu-id="86988-104">Find devices by tag API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="86988-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="86988-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="86988-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="86988-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="86988-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="86988-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="86988-108">Описание API</span><span class="sxs-lookup"><span data-stu-id="86988-108">API description</span></span>
<span data-ttu-id="86988-109">Поиск [машин](machine.md) по [тегу](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="86988-109">Find [Machines](machine.md) by [Tag](machine-tags.md).</span></span>
<br><span data-ttu-id="86988-110">```startswith``` запрос поддерживается.</span><span class="sxs-lookup"><span data-stu-id="86988-110">```startswith``` query is supported.</span></span> 

## <a name="limitations"></a><span data-ttu-id="86988-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="86988-111">Limitations</span></span>
1. <span data-ttu-id="86988-112">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="86988-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="86988-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="86988-113">Permissions</span></span>
<span data-ttu-id="86988-114">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="86988-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="86988-115">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="86988-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="86988-116">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="86988-116">Permission type</span></span> |   <span data-ttu-id="86988-117">Разрешение</span><span class="sxs-lookup"><span data-stu-id="86988-117">Permission</span></span>  |   <span data-ttu-id="86988-118">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="86988-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="86988-119">Application</span><span class="sxs-lookup"><span data-stu-id="86988-119">Application</span></span> |   <span data-ttu-id="86988-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="86988-120">Machine.Read.All</span></span> |  <span data-ttu-id="86988-121">'Read all machine profiles'</span><span class="sxs-lookup"><span data-stu-id="86988-121">'Read all machine profiles'</span></span>
<span data-ttu-id="86988-122">Application</span><span class="sxs-lookup"><span data-stu-id="86988-122">Application</span></span> |   <span data-ttu-id="86988-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="86988-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="86988-124">'Read and write all machine information'</span><span class="sxs-lookup"><span data-stu-id="86988-124">'Read and write all machine information'</span></span>
<span data-ttu-id="86988-125">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="86988-125">Delegated (work or school account)</span></span> | <span data-ttu-id="86988-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="86988-126">Machine.Read</span></span> | <span data-ttu-id="86988-127">'Read machine information'</span><span class="sxs-lookup"><span data-stu-id="86988-127">'Read machine information'</span></span>
<span data-ttu-id="86988-128">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="86988-128">Delegated (work or school account)</span></span> | <span data-ttu-id="86988-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="86988-129">Machine.ReadWrite</span></span> | <span data-ttu-id="86988-130">'Read and write machine information'</span><span class="sxs-lookup"><span data-stu-id="86988-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="86988-131">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="86988-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="86988-132">В ответ будут включены только устройства, к которые пользователь имеет доступ на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="86988-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="86988-133">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="86988-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="86988-134">В ответ будут включены только устройства, к которые пользователь имеет доступ на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="86988-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="86988-135">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="86988-135">HTTP request</span></span>
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a><span data-ttu-id="86988-136">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="86988-136">Request headers</span></span>

<span data-ttu-id="86988-137">Имя</span><span class="sxs-lookup"><span data-stu-id="86988-137">Name</span></span> | <span data-ttu-id="86988-138">Тип</span><span class="sxs-lookup"><span data-stu-id="86988-138">Type</span></span> | <span data-ttu-id="86988-139">Описание</span><span class="sxs-lookup"><span data-stu-id="86988-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="86988-140">Авторизация</span><span class="sxs-lookup"><span data-stu-id="86988-140">Authorization</span></span> | <span data-ttu-id="86988-141">Строка</span><span class="sxs-lookup"><span data-stu-id="86988-141">String</span></span> | <span data-ttu-id="86988-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="86988-142">Bearer {token}.</span></span> <span data-ttu-id="86988-143">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="86988-143">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="86988-144">Запрос параметров URI</span><span class="sxs-lookup"><span data-stu-id="86988-144">Request URI parameters</span></span>

<span data-ttu-id="86988-145">Имя</span><span class="sxs-lookup"><span data-stu-id="86988-145">Name</span></span> | <span data-ttu-id="86988-146">Тип</span><span class="sxs-lookup"><span data-stu-id="86988-146">Type</span></span> | <span data-ttu-id="86988-147">Описание</span><span class="sxs-lookup"><span data-stu-id="86988-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="86988-148">tag</span><span class="sxs-lookup"><span data-stu-id="86988-148">tag</span></span> | <span data-ttu-id="86988-149">Строка</span><span class="sxs-lookup"><span data-stu-id="86988-149">String</span></span> | <span data-ttu-id="86988-150">Имя тега.</span><span class="sxs-lookup"><span data-stu-id="86988-150">The tag name.</span></span> <span data-ttu-id="86988-151">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="86988-151">**Required**.</span></span>
<span data-ttu-id="86988-152">useStartsWithFilter</span><span class="sxs-lookup"><span data-stu-id="86988-152">useStartsWithFilter</span></span> | <span data-ttu-id="86988-153">Boolean</span><span class="sxs-lookup"><span data-stu-id="86988-153">Boolean</span></span> | <span data-ttu-id="86988-154">При наборе true поиск будет находить все устройства с именем тега, которое начинается с данного тега в запросе.</span><span class="sxs-lookup"><span data-stu-id="86988-154">When set to true, the search will find all devices with tag name that starts with the given tag in the query.</span></span> <span data-ttu-id="86988-155">Значение по умолчанию: false.</span><span class="sxs-lookup"><span data-stu-id="86988-155">Defaults to false.</span></span> <span data-ttu-id="86988-156">**Необязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="86988-156">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="86988-157">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="86988-157">Request body</span></span>
<span data-ttu-id="86988-158">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="86988-158">Empty</span></span>

## <a name="response"></a><span data-ttu-id="86988-159">Отклик</span><span class="sxs-lookup"><span data-stu-id="86988-159">Response</span></span>
<span data-ttu-id="86988-160">Если успешно — 200 ОК со списком машин в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="86988-160">If successful - 200 OK with list of the machines in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="86988-161">Пример</span><span class="sxs-lookup"><span data-stu-id="86988-161">Example</span></span>

<span data-ttu-id="86988-162">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="86988-162">**Request**</span></span>

<span data-ttu-id="86988-163">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="86988-163">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```