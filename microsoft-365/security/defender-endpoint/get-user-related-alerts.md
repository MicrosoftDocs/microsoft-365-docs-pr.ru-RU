---
title: Получить API оповещений, связанных с пользователем
description: Извлечение коллекции оповещений, связанных с данным пользовательским ИД с помощью Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, user, related, alerts
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
ms.openlocfilehash: ab0d0e97365b5ce38b29f2b0d65e3aea48d6c28c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769933"
---
# <a name="get-user-related-alerts-api"></a><span data-ttu-id="ab61b-104">Получить API оповещений, связанных с пользователем</span><span class="sxs-lookup"><span data-stu-id="ab61b-104">Get user-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ab61b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ab61b-105">**Applies to:**</span></span>
- [<span data-ttu-id="ab61b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ab61b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ab61b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab61b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ab61b-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ab61b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ab61b-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ab61b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="ab61b-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="ab61b-110">API description</span></span>
<span data-ttu-id="ab61b-111">Извлекает коллекцию оповещений, связанных с данным пользовательским ИД.</span><span class="sxs-lookup"><span data-stu-id="ab61b-111">Retrieves a collection of alerts related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="ab61b-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ab61b-112">Limitations</span></span>
1. <span data-ttu-id="ab61b-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="ab61b-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="ab61b-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="ab61b-114">Permissions</span></span>
<span data-ttu-id="ab61b-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="ab61b-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ab61b-116">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ab61b-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ab61b-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="ab61b-117">Permission type</span></span> |   <span data-ttu-id="ab61b-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="ab61b-118">Permission</span></span>  |   <span data-ttu-id="ab61b-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="ab61b-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ab61b-120">Приложение</span><span class="sxs-lookup"><span data-stu-id="ab61b-120">Application</span></span> |   <span data-ttu-id="ab61b-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="ab61b-121">Alert.Read.All</span></span> |    <span data-ttu-id="ab61b-122">'Read all alerts'</span><span class="sxs-lookup"><span data-stu-id="ab61b-122">'Read all alerts'</span></span>
<span data-ttu-id="ab61b-123">Приложение</span><span class="sxs-lookup"><span data-stu-id="ab61b-123">Application</span></span> |   <span data-ttu-id="ab61b-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="ab61b-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="ab61b-125">'Read and write all alerts'</span><span class="sxs-lookup"><span data-stu-id="ab61b-125">'Read and write all alerts'</span></span>
<span data-ttu-id="ab61b-126">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="ab61b-126">Delegated (work or school account)</span></span> | <span data-ttu-id="ab61b-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="ab61b-127">Alert.Read</span></span> | <span data-ttu-id="ab61b-128">'Read alerts'</span><span class="sxs-lookup"><span data-stu-id="ab61b-128">'Read alerts'</span></span>
<span data-ttu-id="ab61b-129">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="ab61b-129">Delegated (work or school account)</span></span> | <span data-ttu-id="ab61b-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ab61b-130">Alert.ReadWrite</span></span> | <span data-ttu-id="ab61b-131">'Read and write alerts'</span><span class="sxs-lookup"><span data-stu-id="ab61b-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="ab61b-132">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="ab61b-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="ab61b-133">У пользователя должно быть по крайней мере следующее разрешение на роль: "Просмотр данных".</span><span class="sxs-lookup"><span data-stu-id="ab61b-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="ab61b-134">Дополнительные сведения см. в [дополнительных сведениях о создании и управлении ролями.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="ab61b-134">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="ab61b-135">Ответ будет включать только оповещения, связанные с устройствами, к которые пользователь имеет [](machine-groups.md) доступ на основе параметров группы устройств (см. дополнительные сведения о создании и управлении группами устройств).</span><span class="sxs-lookup"><span data-stu-id="ab61b-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="ab61b-136">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="ab61b-136">HTTP request</span></span>
```
GET /api/users/{id}/alerts
```

<span data-ttu-id="ab61b-137">**ID — это не полное имя пользователя, а только имя пользователя. (например, для получения оповещений для user1@contoso.com/api/users/user1/alerts)**</span><span class="sxs-lookup"><span data-stu-id="ab61b-137">**The ID is not the full UPN, but only the user name. (for example, to retrieve alerts for user1@contoso.com use /api/users/user1/alerts)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="ab61b-138">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="ab61b-138">Request headers</span></span>

<span data-ttu-id="ab61b-139">Имя</span><span class="sxs-lookup"><span data-stu-id="ab61b-139">Name</span></span> | <span data-ttu-id="ab61b-140">Тип</span><span class="sxs-lookup"><span data-stu-id="ab61b-140">Type</span></span> | <span data-ttu-id="ab61b-141">Описание</span><span class="sxs-lookup"><span data-stu-id="ab61b-141">Description</span></span>
:---|:---|:---
<span data-ttu-id="ab61b-142">Authorization</span><span class="sxs-lookup"><span data-stu-id="ab61b-142">Authorization</span></span> | <span data-ttu-id="ab61b-143">String</span><span class="sxs-lookup"><span data-stu-id="ab61b-143">String</span></span> | <span data-ttu-id="ab61b-144">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ab61b-144">Bearer {token}.</span></span> <span data-ttu-id="ab61b-145">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="ab61b-145">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ab61b-146">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="ab61b-146">Request body</span></span>
<span data-ttu-id="ab61b-147">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="ab61b-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ab61b-148">Отклик</span><span class="sxs-lookup"><span data-stu-id="ab61b-148">Response</span></span>
<span data-ttu-id="ab61b-149">Если успешно и пользователь существует — 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="ab61b-149">If successful and user exists - 200 OK.</span></span> <span data-ttu-id="ab61b-150">Если пользователя не существует - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="ab61b-150">If the user does not exist - 404 Not Found.</span></span> 


## <a name="example"></a><span data-ttu-id="ab61b-151">Пример</span><span class="sxs-lookup"><span data-stu-id="ab61b-151">Example</span></span>

<span data-ttu-id="ab61b-152">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="ab61b-152">**Request**</span></span>

<span data-ttu-id="ab61b-153">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="ab61b-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```
