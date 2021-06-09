---
title: Получить API машин, связанных с пользователем
description: Узнайте, как использовать API машин get user-related для получения коллекции устройств, связанных с пользовательским ИД в Microsoft Defender for Endpoint.
keywords: apis, graph api, supported apis, get, user, user related alerts
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
ms.openlocfilehash: 230af2311c52437e01cdb28d823236347cf34b8f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769905"
---
# <a name="get-user-related-machines-api"></a><span data-ttu-id="29023-104">Получить API машин, связанных с пользователем</span><span class="sxs-lookup"><span data-stu-id="29023-104">Get user-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="29023-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="29023-105">**Applies to:**</span></span>
- [<span data-ttu-id="29023-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="29023-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="29023-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29023-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="29023-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="29023-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="29023-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="29023-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="29023-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="29023-110">API description</span></span>
<span data-ttu-id="29023-111">Извлекает коллекцию устройств, связанных с данным пользовательским ИД.</span><span class="sxs-lookup"><span data-stu-id="29023-111">Retrieves a collection of devices related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="29023-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="29023-112">Limitations</span></span>
1. <span data-ttu-id="29023-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="29023-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="29023-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="29023-114">Permissions</span></span>
<span data-ttu-id="29023-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="29023-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="29023-116">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="29023-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="29023-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="29023-117">Permission type</span></span> |   <span data-ttu-id="29023-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="29023-118">Permission</span></span>  |   <span data-ttu-id="29023-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="29023-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="29023-120">Приложение</span><span class="sxs-lookup"><span data-stu-id="29023-120">Application</span></span> |   <span data-ttu-id="29023-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="29023-121">Machine.Read.All</span></span> |  <span data-ttu-id="29023-122">'Read all machine profiles'</span><span class="sxs-lookup"><span data-stu-id="29023-122">'Read all machine profiles'</span></span>
<span data-ttu-id="29023-123">Приложение</span><span class="sxs-lookup"><span data-stu-id="29023-123">Application</span></span> |   <span data-ttu-id="29023-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="29023-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="29023-125">'Read and write all machine information'</span><span class="sxs-lookup"><span data-stu-id="29023-125">'Read and write all machine information'</span></span>
<span data-ttu-id="29023-126">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="29023-126">Delegated (work or school account)</span></span> | <span data-ttu-id="29023-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="29023-127">Machine.Read</span></span> | <span data-ttu-id="29023-128">'Read machine information'</span><span class="sxs-lookup"><span data-stu-id="29023-128">'Read machine information'</span></span>
<span data-ttu-id="29023-129">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="29023-129">Delegated (work or school account)</span></span> | <span data-ttu-id="29023-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="29023-130">Machine.ReadWrite</span></span> | <span data-ttu-id="29023-131">'Read and write machine information'</span><span class="sxs-lookup"><span data-stu-id="29023-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="29023-132">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="29023-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="29023-133">У пользователя должно быть по крайней мере следующее разрешение на роль: "Просмотр данных".</span><span class="sxs-lookup"><span data-stu-id="29023-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="29023-134">Дополнительные сведения см. в [дополнительных сведениях о создании и управлении ролями](user-roles.md) )</span><span class="sxs-lookup"><span data-stu-id="29023-134">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="29023-135">Ответ будет включать только устройства, к которые пользователь может получить доступ, в зависимости от параметров группы устройств.</span><span class="sxs-lookup"><span data-stu-id="29023-135">Response will include only devices that the user can access, based on device group settings.</span></span> <span data-ttu-id="29023-136">Дополнительные сведения см. в [дополнительных сведениях о создании и управлении группами устройств.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="29023-136">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="29023-137">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="29023-137">HTTP request</span></span>
```
GET /api/users/{id}/machines
```

<span data-ttu-id="29023-138">**ID — это не полное имя пользователя, а только имя пользователя. (например, для получения машин для user1@contoso.com /api/users/user1/machines)**</span><span class="sxs-lookup"><span data-stu-id="29023-138">**The ID is not the full UPN, but only the user name. (for example, to retrieve machines for user1@contoso.com use /api/users/user1/machines)**</span></span>


## <a name="request-headers"></a><span data-ttu-id="29023-139">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="29023-139">Request headers</span></span>

<span data-ttu-id="29023-140">Имя</span><span class="sxs-lookup"><span data-stu-id="29023-140">Name</span></span> | <span data-ttu-id="29023-141">Тип</span><span class="sxs-lookup"><span data-stu-id="29023-141">Type</span></span> | <span data-ttu-id="29023-142">Описание</span><span class="sxs-lookup"><span data-stu-id="29023-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="29023-143">Авторизация</span><span class="sxs-lookup"><span data-stu-id="29023-143">Authorization</span></span> | <span data-ttu-id="29023-144">String</span><span class="sxs-lookup"><span data-stu-id="29023-144">String</span></span> | <span data-ttu-id="29023-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="29023-145">Bearer {token}.</span></span> <span data-ttu-id="29023-146">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="29023-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="29023-147">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="29023-147">Request body</span></span>
<span data-ttu-id="29023-148">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="29023-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="29023-149">Отклик</span><span class="sxs-lookup"><span data-stu-id="29023-149">Response</span></span>
<span data-ttu-id="29023-150">При успешном и удобном пользователе — [](machine.md) 200 ОК со списком машинных сущностями в теле.</span><span class="sxs-lookup"><span data-stu-id="29023-150">If successful and user exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="29023-151">Если пользователя не существует - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="29023-151">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="29023-152">Пример</span><span class="sxs-lookup"><span data-stu-id="29023-152">Example</span></span>

<span data-ttu-id="29023-153">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="29023-153">**Request**</span></span>

<span data-ttu-id="29023-154">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="29023-154">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
