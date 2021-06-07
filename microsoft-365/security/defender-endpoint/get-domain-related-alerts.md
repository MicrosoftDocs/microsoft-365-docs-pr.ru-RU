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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c5de779566f1aa8e53da10b9aa5bceb92f5a0a3c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772261"
---
# <a name="get-domain-related-alerts-api"></a><span data-ttu-id="65aae-104">Получить API оповещений, связанных с доменом</span><span class="sxs-lookup"><span data-stu-id="65aae-104">Get domain-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="65aae-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="65aae-105">**Applies to:**</span></span>
- [<span data-ttu-id="65aae-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="65aae-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="65aae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65aae-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="65aae-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="65aae-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="65aae-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="65aae-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="65aae-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="65aae-110">API description</span></span>
<span data-ttu-id="65aae-111">Извлекает коллекцию [оповещений, связанных](alerts.md) с заданным доменным адресом.</span><span class="sxs-lookup"><span data-stu-id="65aae-111">Retrieves a collection of [Alerts](alerts.md) related to a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="65aae-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="65aae-112">Limitations</span></span>
1. <span data-ttu-id="65aae-113">Вы можете запрашивать последние обновления оповещений в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="65aae-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="65aae-114">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="65aae-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="65aae-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="65aae-115">Permissions</span></span>
<span data-ttu-id="65aae-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="65aae-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="65aae-117">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="65aae-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="65aae-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="65aae-118">Permission type</span></span> |   <span data-ttu-id="65aae-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="65aae-119">Permission</span></span>  |   <span data-ttu-id="65aae-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="65aae-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="65aae-121">Приложение</span><span class="sxs-lookup"><span data-stu-id="65aae-121">Application</span></span> |   <span data-ttu-id="65aae-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="65aae-122">Alert.Read.All</span></span> |    <span data-ttu-id="65aae-123">'Read all alerts'</span><span class="sxs-lookup"><span data-stu-id="65aae-123">'Read all alerts'</span></span>
<span data-ttu-id="65aae-124">Приложение</span><span class="sxs-lookup"><span data-stu-id="65aae-124">Application</span></span> |   <span data-ttu-id="65aae-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="65aae-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="65aae-126">'Read and write all alerts'</span><span class="sxs-lookup"><span data-stu-id="65aae-126">'Read and write all alerts'</span></span>
<span data-ttu-id="65aae-127">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="65aae-127">Delegated (work or school account)</span></span> | <span data-ttu-id="65aae-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="65aae-128">Alert.Read</span></span> | <span data-ttu-id="65aae-129">'Read alerts'</span><span class="sxs-lookup"><span data-stu-id="65aae-129">'Read alerts'</span></span>
<span data-ttu-id="65aae-130">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="65aae-130">Delegated (work or school account)</span></span> | <span data-ttu-id="65aae-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="65aae-131">Alert.ReadWrite</span></span> | <span data-ttu-id="65aae-132">'Read and write alerts'</span><span class="sxs-lookup"><span data-stu-id="65aae-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="65aae-133">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="65aae-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="65aae-134">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="65aae-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="65aae-135">Ответ будет включать только оповещения, связанные с устройствами, к которые пользователь имеет [](machine-groups.md) доступ на основе параметров группы устройств (см. дополнительные сведения о создании и управлении группами устройств).</span><span class="sxs-lookup"><span data-stu-id="65aae-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="65aae-136">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="65aae-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="65aae-137">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="65aae-137">Request headers</span></span>

| <span data-ttu-id="65aae-138">Заголовок</span><span class="sxs-lookup"><span data-stu-id="65aae-138">Header</span></span>        | <span data-ttu-id="65aae-139">Значение</span><span class="sxs-lookup"><span data-stu-id="65aae-139">Value</span></span>  |
|:--------------|:-------|
| <span data-ttu-id="65aae-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="65aae-140">Authorization</span></span> | <span data-ttu-id="65aae-141">String</span><span class="sxs-lookup"><span data-stu-id="65aae-141">String</span></span> |

## <a name="request-body"></a><span data-ttu-id="65aae-142">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="65aae-142">Request body</span></span>
<span data-ttu-id="65aae-143">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="65aae-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="65aae-144">Отклик</span><span class="sxs-lookup"><span data-stu-id="65aae-144">Response</span></span>
<span data-ttu-id="65aae-145">При успешном и доменном доступе — 200 ОК со списком сущностями [оповещений.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="65aae-145">If successful and domain exists - 200 OK with list of [alert](alerts.md) entities.</span></span> <span data-ttu-id="65aae-146">Если домена не существует - 404 Не найден.</span><span class="sxs-lookup"><span data-stu-id="65aae-146">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="65aae-147">Пример</span><span class="sxs-lookup"><span data-stu-id="65aae-147">Example</span></span>

<span data-ttu-id="65aae-148">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="65aae-148">**Request**</span></span>

<span data-ttu-id="65aae-149">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="65aae-149">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
