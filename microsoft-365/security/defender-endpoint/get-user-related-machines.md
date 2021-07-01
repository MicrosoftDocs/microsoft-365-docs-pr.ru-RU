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
ms.openlocfilehash: ead0558bfff90c29ec8717fbb39876afda5c42af
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229459"
---
# <a name="get-user-related-machines-api"></a><span data-ttu-id="c3051-104">Получить API машин, связанных с пользователем</span><span class="sxs-lookup"><span data-stu-id="c3051-104">Get user-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c3051-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c3051-105">**Applies to:**</span></span>
- [<span data-ttu-id="c3051-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c3051-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c3051-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3051-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c3051-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c3051-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c3051-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c3051-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="c3051-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="c3051-110">API description</span></span>
<span data-ttu-id="c3051-111">Извлекает коллекцию устройств, связанных с данным пользовательским ИД.</span><span class="sxs-lookup"><span data-stu-id="c3051-111">Retrieves a collection of devices related to a given user ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="c3051-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c3051-112">Limitations</span></span>

<span data-ttu-id="c3051-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="c3051-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="c3051-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="c3051-114">Permissions</span></span>

<span data-ttu-id="c3051-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="c3051-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c3051-116">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c3051-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c3051-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="c3051-117">Permission type</span></span> |<span data-ttu-id="c3051-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="c3051-118">Permission</span></span>|<span data-ttu-id="c3051-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="c3051-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c3051-120">Приложение</span><span class="sxs-lookup"><span data-stu-id="c3051-120">Application</span></span> |<span data-ttu-id="c3051-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="c3051-121">Machine.Read.All</span></span>|<span data-ttu-id="c3051-122">'Read all machine profiles'</span><span class="sxs-lookup"><span data-stu-id="c3051-122">'Read all machine profiles'</span></span>
<span data-ttu-id="c3051-123">Приложение</span><span class="sxs-lookup"><span data-stu-id="c3051-123">Application</span></span> |<span data-ttu-id="c3051-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c3051-124">Machine.ReadWrite.All</span></span> |<span data-ttu-id="c3051-125">'Read and write all machine information'</span><span class="sxs-lookup"><span data-stu-id="c3051-125">'Read and write all machine information'</span></span>
<span data-ttu-id="c3051-126">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="c3051-126">Delegated (work or school account)</span></span> | <span data-ttu-id="c3051-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="c3051-127">Machine.Read</span></span> | <span data-ttu-id="c3051-128">'Read machine information'</span><span class="sxs-lookup"><span data-stu-id="c3051-128">'Read machine information'</span></span>
<span data-ttu-id="c3051-129">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="c3051-129">Delegated (work or school account)</span></span> | <span data-ttu-id="c3051-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c3051-130">Machine.ReadWrite</span></span> | <span data-ttu-id="c3051-131">'Read and write machine information'</span><span class="sxs-lookup"><span data-stu-id="c3051-131">'Read and write machine information'</span></span>

> [!NOTE]
> <span data-ttu-id="c3051-132">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="c3051-132">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="c3051-133">У пользователя должно быть по крайней мере следующее разрешение на роль: "Просмотр данных".</span><span class="sxs-lookup"><span data-stu-id="c3051-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="c3051-134">Дополнительные сведения см. в [дополнительных сведениях о создании и управлении ролями](user-roles.md))</span><span class="sxs-lookup"><span data-stu-id="c3051-134">For more information, see [Create and manage roles](user-roles.md))</span></span>
> - <span data-ttu-id="c3051-135">Ответ будет включать только устройства, к которые пользователь может получить доступ, в зависимости от параметров группы устройств.</span><span class="sxs-lookup"><span data-stu-id="c3051-135">Response will include only devices that the user can access, based on device group settings.</span></span> <span data-ttu-id="c3051-136">Дополнительные сведения см. в [дополнительных сведениях о создании и управлении группами устройств.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="c3051-136">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="c3051-137">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="c3051-137">HTTP request</span></span>

```http
GET /api/users/{id}/machines
```

<span data-ttu-id="c3051-138">**ID — это не полное имя пользователя, а только имя пользователя. (например, для получения машин для user1@contoso.com /api/users/user1/machines)**</span><span class="sxs-lookup"><span data-stu-id="c3051-138">**The ID is not the full UPN, but only the user name. (for example, to retrieve machines for user1@contoso.com use /api/users/user1/machines)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="c3051-139">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="c3051-139">Request headers</span></span>

<span data-ttu-id="c3051-140">Имя</span><span class="sxs-lookup"><span data-stu-id="c3051-140">Name</span></span> | <span data-ttu-id="c3051-141">Тип</span><span class="sxs-lookup"><span data-stu-id="c3051-141">Type</span></span> | <span data-ttu-id="c3051-142">Описание</span><span class="sxs-lookup"><span data-stu-id="c3051-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="c3051-143">Авторизация</span><span class="sxs-lookup"><span data-stu-id="c3051-143">Authorization</span></span> | <span data-ttu-id="c3051-144">String</span><span class="sxs-lookup"><span data-stu-id="c3051-144">String</span></span> | <span data-ttu-id="c3051-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c3051-145">Bearer {token}.</span></span> <span data-ttu-id="c3051-146">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="c3051-146">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c3051-147">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="c3051-147">Request body</span></span>

<span data-ttu-id="c3051-148">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="c3051-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c3051-149">Отклик</span><span class="sxs-lookup"><span data-stu-id="c3051-149">Response</span></span>

<span data-ttu-id="c3051-150">При успешном и удобном пользователе — [](machine.md) 200 ОК со списком машинных сущностями в теле.</span><span class="sxs-lookup"><span data-stu-id="c3051-150">If successful and user exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="c3051-151">Если пользователя не существует - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="c3051-151">If user does not exist - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="c3051-152">Пример</span><span class="sxs-lookup"><span data-stu-id="c3051-152">Example</span></span>

### <a name="request"></a><span data-ttu-id="c3051-153">Запрос</span><span class="sxs-lookup"><span data-stu-id="c3051-153">Request</span></span>

<span data-ttu-id="c3051-154">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="c3051-154">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
