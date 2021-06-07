---
title: Получать сведения об оповещении по API ID
description: Узнайте, как использовать сведения о оповещении по API ID для получения определенного оповещений по его ID в Microsoft Defender for Endpoint.
keywords: apis, api graph, supported apis, get, alert, information, id
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
ms.openlocfilehash: b9de7645abc59849b3ca28f64904b0ba49d4eef5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771901"
---
# <a name="get-alert-information-by-id-api"></a><span data-ttu-id="2fbb5-104">Получать сведения об оповещении по API ID</span><span class="sxs-lookup"><span data-stu-id="2fbb5-104">Get alert information by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2fbb5-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2fbb5-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="2fbb5-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="2fbb5-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2fbb5-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="2fbb5-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2fbb5-108">Описание API</span><span class="sxs-lookup"><span data-stu-id="2fbb5-108">API description</span></span>
<span data-ttu-id="2fbb5-109">Извлекает определенное [оповещение](alerts.md) по его ID.</span><span class="sxs-lookup"><span data-stu-id="2fbb5-109">Retrieves specific [Alert](alerts.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="2fbb5-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2fbb5-110">Limitations</span></span>
1. <span data-ttu-id="2fbb5-111">Вы можете получать последние обновления оповещений в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="2fbb5-111">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="2fbb5-112">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="2fbb5-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="2fbb5-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="2fbb5-113">Permissions</span></span>
<span data-ttu-id="2fbb5-114">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="2fbb5-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2fbb5-115">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2fbb5-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2fbb5-116">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="2fbb5-116">Permission type</span></span> |   <span data-ttu-id="2fbb5-117">Разрешение</span><span class="sxs-lookup"><span data-stu-id="2fbb5-117">Permission</span></span>  |   <span data-ttu-id="2fbb5-118">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="2fbb5-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2fbb5-119">Приложение</span><span class="sxs-lookup"><span data-stu-id="2fbb5-119">Application</span></span> |   <span data-ttu-id="2fbb5-120">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="2fbb5-120">Alert.Read.All</span></span> |    <span data-ttu-id="2fbb5-121">'Read all alerts'</span><span class="sxs-lookup"><span data-stu-id="2fbb5-121">'Read all alerts'</span></span>
<span data-ttu-id="2fbb5-122">Приложение</span><span class="sxs-lookup"><span data-stu-id="2fbb5-122">Application</span></span> |   <span data-ttu-id="2fbb5-123">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="2fbb5-123">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="2fbb5-124">'Read and write all alerts'</span><span class="sxs-lookup"><span data-stu-id="2fbb5-124">'Read and write all alerts'</span></span>
<span data-ttu-id="2fbb5-125">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="2fbb5-125">Delegated (work or school account)</span></span> | <span data-ttu-id="2fbb5-126">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="2fbb5-126">Alert.Read</span></span> | <span data-ttu-id="2fbb5-127">'Read alerts'</span><span class="sxs-lookup"><span data-stu-id="2fbb5-127">'Read alerts'</span></span>
<span data-ttu-id="2fbb5-128">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="2fbb5-128">Delegated (work or school account)</span></span> | <span data-ttu-id="2fbb5-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="2fbb5-129">Alert.ReadWrite</span></span> | <span data-ttu-id="2fbb5-130">'Read and write alerts'</span><span class="sxs-lookup"><span data-stu-id="2fbb5-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="2fbb5-131">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="2fbb5-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2fbb5-132">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="2fbb5-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="2fbb5-133">Пользователь должен иметь доступ к устройству, связанному с оповещением, на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="2fbb5-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2fbb5-134">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="2fbb5-134">HTTP request</span></span>
```
GET /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="2fbb5-135">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="2fbb5-135">Request headers</span></span>

<span data-ttu-id="2fbb5-136">Имя</span><span class="sxs-lookup"><span data-stu-id="2fbb5-136">Name</span></span> | <span data-ttu-id="2fbb5-137">Тип</span><span class="sxs-lookup"><span data-stu-id="2fbb5-137">Type</span></span> | <span data-ttu-id="2fbb5-138">Описание</span><span class="sxs-lookup"><span data-stu-id="2fbb5-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="2fbb5-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="2fbb5-139">Authorization</span></span> | <span data-ttu-id="2fbb5-140">String</span><span class="sxs-lookup"><span data-stu-id="2fbb5-140">String</span></span> | <span data-ttu-id="2fbb5-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2fbb5-141">Bearer {token}.</span></span> <span data-ttu-id="2fbb5-142">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="2fbb5-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="2fbb5-143">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="2fbb5-143">Request body</span></span>
<span data-ttu-id="2fbb5-144">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="2fbb5-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2fbb5-145">Отклик</span><span class="sxs-lookup"><span data-stu-id="2fbb5-145">Response</span></span>
<span data-ttu-id="2fbb5-146">В случае успешной работы этот метод возвращает [](alerts.md) 200 ОК и объект оповещения в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="2fbb5-146">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body.</span></span> <span data-ttu-id="2fbb5-147">Если оповещение с указанным id не найдено - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="2fbb5-147">If alert with the specified id was not found - 404 Not Found.</span></span>
