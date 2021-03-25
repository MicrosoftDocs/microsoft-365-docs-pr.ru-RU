---
title: Получить API оповещений, связанных с машиной
description: Узнайте, как использовать API оповещений, связанных с машиной, для получения всех оповещений, связанных с определенным устройством в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, devices, related, alerts
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
ms.openlocfilehash: 837643bf5793437380a6f33c0eeca55ccef2100b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199255"
---
# <a name="get-machine-related-alerts--api"></a><span data-ttu-id="35b89-104">Получить API оповещений, связанных с машиной</span><span class="sxs-lookup"><span data-stu-id="35b89-104">Get machine related alerts  API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="35b89-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="35b89-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="35b89-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="35b89-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="35b89-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="35b89-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="35b89-108">Описание API</span><span class="sxs-lookup"><span data-stu-id="35b89-108">API description</span></span>
<span data-ttu-id="35b89-109">Извлекает все [оповещения, связанные](alerts.md) с определенным устройством.</span><span class="sxs-lookup"><span data-stu-id="35b89-109">Retrieves all [Alerts](alerts.md) related to a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="35b89-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="35b89-110">Limitations</span></span>
1. <span data-ttu-id="35b89-111">Вы можете запрашивать на устройствах последнее обновление в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="35b89-111">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="35b89-112">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="35b89-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


<span data-ttu-id="35b89-113">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="35b89-113">Permission type</span></span> |   <span data-ttu-id="35b89-114">Разрешение</span><span class="sxs-lookup"><span data-stu-id="35b89-114">Permission</span></span>  |   <span data-ttu-id="35b89-115">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="35b89-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="35b89-116">Application</span><span class="sxs-lookup"><span data-stu-id="35b89-116">Application</span></span> |   <span data-ttu-id="35b89-117">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="35b89-117">Alert.Read.All</span></span> |    <span data-ttu-id="35b89-118">'Read all alerts'</span><span class="sxs-lookup"><span data-stu-id="35b89-118">'Read all alerts'</span></span>
<span data-ttu-id="35b89-119">Application</span><span class="sxs-lookup"><span data-stu-id="35b89-119">Application</span></span> |   <span data-ttu-id="35b89-120">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="35b89-120">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="35b89-121">'Read and write all alerts'</span><span class="sxs-lookup"><span data-stu-id="35b89-121">'Read and write all alerts'</span></span>
<span data-ttu-id="35b89-122">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="35b89-122">Delegated (work or school account)</span></span> | <span data-ttu-id="35b89-123">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="35b89-123">Alert.Read</span></span> | <span data-ttu-id="35b89-124">'Read alerts'</span><span class="sxs-lookup"><span data-stu-id="35b89-124">'Read alerts'</span></span>
<span data-ttu-id="35b89-125">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="35b89-125">Delegated (work or school account)</span></span> | <span data-ttu-id="35b89-126">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="35b89-126">Alert.ReadWrite</span></span> | <span data-ttu-id="35b89-127">'Read and write alerts'</span><span class="sxs-lookup"><span data-stu-id="35b89-127">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="35b89-128">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="35b89-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="35b89-129">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="35b89-129">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="35b89-130">Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="35b89-130">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="35b89-131">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="35b89-131">HTTP request</span></span>
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="35b89-132">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="35b89-132">Request headers</span></span>

<span data-ttu-id="35b89-133">Имя</span><span class="sxs-lookup"><span data-stu-id="35b89-133">Name</span></span> | <span data-ttu-id="35b89-134">Тип</span><span class="sxs-lookup"><span data-stu-id="35b89-134">Type</span></span> | <span data-ttu-id="35b89-135">Описание</span><span class="sxs-lookup"><span data-stu-id="35b89-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="35b89-136">Авторизация</span><span class="sxs-lookup"><span data-stu-id="35b89-136">Authorization</span></span> | <span data-ttu-id="35b89-137">Строка</span><span class="sxs-lookup"><span data-stu-id="35b89-137">String</span></span> | <span data-ttu-id="35b89-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="35b89-138">Bearer {token}.</span></span> <span data-ttu-id="35b89-139">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="35b89-139">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="35b89-140">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="35b89-140">Request body</span></span>
<span data-ttu-id="35b89-141">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="35b89-141">Empty</span></span>

## <a name="response"></a><span data-ttu-id="35b89-142">Отклик</span><span class="sxs-lookup"><span data-stu-id="35b89-142">Response</span></span>
<span data-ttu-id="35b89-143">При успешном и устройстве существует — [](alerts.md) 200 ОК со списком сущностями оповещения в теле.</span><span class="sxs-lookup"><span data-stu-id="35b89-143">If successful and device exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="35b89-144">Если устройство не найдено - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="35b89-144">If device was not found - 404 Not Found.</span></span>
