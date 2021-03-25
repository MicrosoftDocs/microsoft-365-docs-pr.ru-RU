---
title: Поиск устройств с помощью внутреннего API IP
description: Поиск устройств с запрашиваемой внутренней IP-адресой в диапазоне времени за 15 минут до и после заданного времени
keywords: apis, api graph, supported apis, get, device, IP, find, find device, by ip, ip
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
ms.openlocfilehash: fa523a7f9b997f3a8d36dff42d10c1229e7a467f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200441"
---
# <a name="find-devices-by-internal-ip-api"></a><span data-ttu-id="dd75c-104">Поиск устройств с помощью внутреннего API IP</span><span class="sxs-lookup"><span data-stu-id="dd75c-104">Find devices by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="dd75c-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="dd75c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="dd75c-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="dd75c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dd75c-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="dd75c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="dd75c-108">Описание API</span><span class="sxs-lookup"><span data-stu-id="dd75c-108">API description</span></span>
<span data-ttu-id="dd75c-109">Поиск [машин](machine.md) с запрашиваемой внутренней IP-адресой в диапазоне времени за 15 минут до и после заданного времени.</span><span class="sxs-lookup"><span data-stu-id="dd75c-109">Find [Machines](machine.md) seen with the requested internal IP in the time range of 15 minutes prior and after a given timestamp.</span></span>


## <a name="limitations"></a><span data-ttu-id="dd75c-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="dd75c-110">Limitations</span></span>
1. <span data-ttu-id="dd75c-111">Данный период времени должен быть в течение последних 30 дней.</span><span class="sxs-lookup"><span data-stu-id="dd75c-111">The given timestamp must be in the past 30 days.</span></span>
2. <span data-ttu-id="dd75c-112">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="dd75c-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="dd75c-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="dd75c-113">Permissions</span></span>
<span data-ttu-id="dd75c-114">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="dd75c-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="dd75c-115">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="dd75c-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="dd75c-116">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="dd75c-116">Permission type</span></span> |   <span data-ttu-id="dd75c-117">Разрешение</span><span class="sxs-lookup"><span data-stu-id="dd75c-117">Permission</span></span>  |   <span data-ttu-id="dd75c-118">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="dd75c-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="dd75c-119">Application</span><span class="sxs-lookup"><span data-stu-id="dd75c-119">Application</span></span> |   <span data-ttu-id="dd75c-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="dd75c-120">Machine.Read.All</span></span> |  <span data-ttu-id="dd75c-121">'Read all machine profiles'</span><span class="sxs-lookup"><span data-stu-id="dd75c-121">'Read all machine profiles'</span></span>
<span data-ttu-id="dd75c-122">Application</span><span class="sxs-lookup"><span data-stu-id="dd75c-122">Application</span></span> |   <span data-ttu-id="dd75c-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="dd75c-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="dd75c-124">'Read and write all machine information'</span><span class="sxs-lookup"><span data-stu-id="dd75c-124">'Read and write all machine information'</span></span>
<span data-ttu-id="dd75c-125">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="dd75c-125">Delegated (work or school account)</span></span> | <span data-ttu-id="dd75c-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="dd75c-126">Machine.Read</span></span> | <span data-ttu-id="dd75c-127">'Read machine information'</span><span class="sxs-lookup"><span data-stu-id="dd75c-127">'Read machine information'</span></span>
<span data-ttu-id="dd75c-128">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="dd75c-128">Delegated (work or school account)</span></span> | <span data-ttu-id="dd75c-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="dd75c-129">Machine.ReadWrite</span></span> | <span data-ttu-id="dd75c-130">'Read and write machine information'</span><span class="sxs-lookup"><span data-stu-id="dd75c-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="dd75c-131">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="dd75c-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="dd75c-132">В ответ будут включены только устройства, к которые пользователь имеет доступ на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="dd75c-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="dd75c-133">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="dd75c-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="dd75c-134">В ответ будут включены только устройства, к которые пользователь имеет доступ на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="dd75c-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="dd75c-135">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="dd75c-135">HTTP request</span></span>
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a><span data-ttu-id="dd75c-136">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="dd75c-136">Request headers</span></span>

<span data-ttu-id="dd75c-137">Имя</span><span class="sxs-lookup"><span data-stu-id="dd75c-137">Name</span></span> | <span data-ttu-id="dd75c-138">Тип</span><span class="sxs-lookup"><span data-stu-id="dd75c-138">Type</span></span> | <span data-ttu-id="dd75c-139">Описание</span><span class="sxs-lookup"><span data-stu-id="dd75c-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="dd75c-140">Авторизация</span><span class="sxs-lookup"><span data-stu-id="dd75c-140">Authorization</span></span> | <span data-ttu-id="dd75c-141">Строка</span><span class="sxs-lookup"><span data-stu-id="dd75c-141">String</span></span> | <span data-ttu-id="dd75c-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="dd75c-142">Bearer {token}.</span></span> <span data-ttu-id="dd75c-143">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="dd75c-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="dd75c-144">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="dd75c-144">Request body</span></span>
<span data-ttu-id="dd75c-145">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="dd75c-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="dd75c-146">Отклик</span><span class="sxs-lookup"><span data-stu-id="dd75c-146">Response</span></span>
<span data-ttu-id="dd75c-147">Если успешно — 200 ОК со списком машин в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="dd75c-147">If successful - 200 OK with list of the machines in the response body.</span></span>
<span data-ttu-id="dd75c-148">Если время не в течение последних 30 дней - 400 bad request.</span><span class="sxs-lookup"><span data-stu-id="dd75c-148">If the timestamp is not in the past 30 days - 400 Bad Request.</span></span>

## <a name="example"></a><span data-ttu-id="dd75c-149">Пример</span><span class="sxs-lookup"><span data-stu-id="dd75c-149">Example</span></span>

<span data-ttu-id="dd75c-150">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="dd75c-150">**Request**</span></span>

<span data-ttu-id="dd75c-151">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="dd75c-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```