---
title: Получить API объекта исследования
description: Используйте этот API для создания вызовов, связанных с тем, чтобы получить объект Investigation
keywords: apis, graph api, supported apis, Investigation object
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
ms.openlocfilehash: 001b8dcf4b0bfd2550f41454fc840602a6e4361f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770137"
---
# <a name="get-investigation-api"></a><span data-ttu-id="9d4ef-104">Получить API исследования</span><span class="sxs-lookup"><span data-stu-id="9d4ef-104">Get Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9d4ef-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9d4ef-105">**Applies to:**</span></span>
- [<span data-ttu-id="9d4ef-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9d4ef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9d4ef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d4ef-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9d4ef-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="9d4ef-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9d4ef-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="9d4ef-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="9d4ef-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="9d4ef-110">API description</span></span>
<span data-ttu-id="9d4ef-111">Извлекает [определенное исследование](investigation.md) по его ID.</span><span class="sxs-lookup"><span data-stu-id="9d4ef-111">Retrieves specific [Investigation](investigation.md) by its ID.</span></span>
<br> <span data-ttu-id="9d4ef-112">ID может быть ИД расследования или проверки, запускающие оповещение.</span><span class="sxs-lookup"><span data-stu-id="9d4ef-112">ID can be the investigation ID or the investigation triggering alert ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="9d4ef-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="9d4ef-113">Limitations</span></span>
1. <span data-ttu-id="9d4ef-114">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="9d4ef-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="9d4ef-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="9d4ef-115">Permissions</span></span>
<span data-ttu-id="9d4ef-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="9d4ef-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9d4ef-117">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9d4ef-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9d4ef-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="9d4ef-118">Permission type</span></span> |   <span data-ttu-id="9d4ef-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="9d4ef-119">Permission</span></span>  |   <span data-ttu-id="9d4ef-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="9d4ef-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9d4ef-121">Приложение</span><span class="sxs-lookup"><span data-stu-id="9d4ef-121">Application</span></span> |   <span data-ttu-id="9d4ef-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="9d4ef-122">Alert.Read.All</span></span> |    <span data-ttu-id="9d4ef-123">'Read all alerts'</span><span class="sxs-lookup"><span data-stu-id="9d4ef-123">'Read all alerts'</span></span>
<span data-ttu-id="9d4ef-124">Приложение</span><span class="sxs-lookup"><span data-stu-id="9d4ef-124">Application</span></span> |   <span data-ttu-id="9d4ef-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9d4ef-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="9d4ef-126">'Read and write all alerts'</span><span class="sxs-lookup"><span data-stu-id="9d4ef-126">'Read and write all alerts'</span></span>
<span data-ttu-id="9d4ef-127">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="9d4ef-127">Delegated (work or school account)</span></span> | <span data-ttu-id="9d4ef-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="9d4ef-128">Alert.Read</span></span> | <span data-ttu-id="9d4ef-129">'Read alerts'</span><span class="sxs-lookup"><span data-stu-id="9d4ef-129">'Read alerts'</span></span>
<span data-ttu-id="9d4ef-130">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="9d4ef-130">Delegated (work or school account)</span></span> | <span data-ttu-id="9d4ef-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9d4ef-131">Alert.ReadWrite</span></span> | <span data-ttu-id="9d4ef-132">'Read and write alerts'</span><span class="sxs-lookup"><span data-stu-id="9d4ef-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="9d4ef-133">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="9d4ef-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9d4ef-134">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="9d4ef-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9d4ef-135">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="9d4ef-135">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="9d4ef-136">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="9d4ef-136">Request headers</span></span>

<span data-ttu-id="9d4ef-137">Имя</span><span class="sxs-lookup"><span data-stu-id="9d4ef-137">Name</span></span> | <span data-ttu-id="9d4ef-138">Тип</span><span class="sxs-lookup"><span data-stu-id="9d4ef-138">Type</span></span> | <span data-ttu-id="9d4ef-139">Описание</span><span class="sxs-lookup"><span data-stu-id="9d4ef-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="9d4ef-140">Авторизация</span><span class="sxs-lookup"><span data-stu-id="9d4ef-140">Authorization</span></span> | <span data-ttu-id="9d4ef-141">String</span><span class="sxs-lookup"><span data-stu-id="9d4ef-141">String</span></span> | <span data-ttu-id="9d4ef-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="9d4ef-142">Bearer {token}.</span></span> <span data-ttu-id="9d4ef-143">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="9d4ef-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9d4ef-144">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="9d4ef-144">Request body</span></span>
<span data-ttu-id="9d4ef-145">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="9d4ef-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9d4ef-146">Отклик</span><span class="sxs-lookup"><span data-stu-id="9d4ef-146">Response</span></span>
<span data-ttu-id="9d4ef-147">В случае успешной работы этот метод возвращает код ответа 200 Ok с [объектом Investigations.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="9d4ef-147">If successful, this method returns 200, Ok response code with a [Investigations](investigation.md) entity.</span></span>

