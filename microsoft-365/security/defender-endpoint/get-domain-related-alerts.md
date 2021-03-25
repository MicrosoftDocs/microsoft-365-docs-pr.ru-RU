---
title: Получить API оповещений, связанных с доменом
description: Узнайте, как использовать API оповещений, связанных с доменом, для получения оповещений, связанных с заданным доменным адресом в Microsoft Defender for Endpoint.
keywords: apis, graph api, supported apis, get, domain, related, alerts
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
ms.technology: mde
ms.openlocfilehash: f8de54072c0b0ebef69b8e5586fee058b971c51f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166867"
---
# <a name="get-domain-related-alerts-api"></a><span data-ttu-id="809dd-104">Получить API оповещений, связанных с доменом</span><span class="sxs-lookup"><span data-stu-id="809dd-104">Get domain-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="809dd-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="809dd-105">**Applies to:**</span></span>
- [<span data-ttu-id="809dd-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="809dd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="809dd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="809dd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="809dd-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="809dd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="809dd-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="809dd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="809dd-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="809dd-110">API description</span></span>
<span data-ttu-id="809dd-111">Извлекает коллекцию [оповещений, связанных](alerts.md) с заданным доменным адресом.</span><span class="sxs-lookup"><span data-stu-id="809dd-111">Retrieves a collection of [Alerts](alerts.md) related to a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="809dd-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="809dd-112">Limitations</span></span>
1. <span data-ttu-id="809dd-113">Вы можете запрашивать последние обновления оповещений в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="809dd-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="809dd-114">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="809dd-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="809dd-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="809dd-115">Permissions</span></span>
<span data-ttu-id="809dd-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="809dd-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="809dd-117">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="809dd-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="809dd-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="809dd-118">Permission type</span></span> |   <span data-ttu-id="809dd-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="809dd-119">Permission</span></span>  |   <span data-ttu-id="809dd-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="809dd-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="809dd-121">Приложение</span><span class="sxs-lookup"><span data-stu-id="809dd-121">Application</span></span> |   <span data-ttu-id="809dd-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="809dd-122">Alert.Read.All</span></span> |    <span data-ttu-id="809dd-123">'Read all alerts'</span><span class="sxs-lookup"><span data-stu-id="809dd-123">'Read all alerts'</span></span>
<span data-ttu-id="809dd-124">Приложение</span><span class="sxs-lookup"><span data-stu-id="809dd-124">Application</span></span> |   <span data-ttu-id="809dd-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="809dd-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="809dd-126">'Read and write all alerts'</span><span class="sxs-lookup"><span data-stu-id="809dd-126">'Read and write all alerts'</span></span>
<span data-ttu-id="809dd-127">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="809dd-127">Delegated (work or school account)</span></span> | <span data-ttu-id="809dd-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="809dd-128">Alert.Read</span></span> | <span data-ttu-id="809dd-129">'Read alerts'</span><span class="sxs-lookup"><span data-stu-id="809dd-129">'Read alerts'</span></span>
<span data-ttu-id="809dd-130">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="809dd-130">Delegated (work or school account)</span></span> | <span data-ttu-id="809dd-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="809dd-131">Alert.ReadWrite</span></span> | <span data-ttu-id="809dd-132">'Read and write alerts'</span><span class="sxs-lookup"><span data-stu-id="809dd-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="809dd-133">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="809dd-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="809dd-134">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="809dd-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="809dd-135">Ответ будет включать только оповещения, связанные с устройствами, к которые пользователь имеет [](machine-groups.md) доступ на основе параметров группы устройств (см. дополнительные сведения о создании и управлении группами устройств).</span><span class="sxs-lookup"><span data-stu-id="809dd-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="809dd-136">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="809dd-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="809dd-137">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="809dd-137">Request headers</span></span>

| <span data-ttu-id="809dd-138">Заголовок</span><span class="sxs-lookup"><span data-stu-id="809dd-138">Header</span></span>        | <span data-ttu-id="809dd-139">Значение</span><span class="sxs-lookup"><span data-stu-id="809dd-139">Value</span></span>  |
|:--------------|:-------|
| <span data-ttu-id="809dd-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="809dd-140">Authorization</span></span> | <span data-ttu-id="809dd-141">Строка</span><span class="sxs-lookup"><span data-stu-id="809dd-141">String</span></span> |

## <a name="request-body"></a><span data-ttu-id="809dd-142">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="809dd-142">Request body</span></span>
<span data-ttu-id="809dd-143">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="809dd-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="809dd-144">Отклик</span><span class="sxs-lookup"><span data-stu-id="809dd-144">Response</span></span>
<span data-ttu-id="809dd-145">При успешном и доменном доступе — 200 ОК со списком сущностями [оповещений.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="809dd-145">If successful and domain exists - 200 OK with list of [alert](alerts.md) entities.</span></span> <span data-ttu-id="809dd-146">Если домена не существует - 404 Не найден.</span><span class="sxs-lookup"><span data-stu-id="809dd-146">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="809dd-147">Пример</span><span class="sxs-lookup"><span data-stu-id="809dd-147">Example</span></span>

<span data-ttu-id="809dd-148">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="809dd-148">**Request**</span></span>

<span data-ttu-id="809dd-149">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="809dd-149">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
