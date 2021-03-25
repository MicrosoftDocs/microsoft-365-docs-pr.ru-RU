---
title: Получить API связанных с доменом машин
description: Узнайте, как использовать API связанных с доменом машин Get для получения машин, которые общались с доменом в Microsoft Defender для конечной точки или из него.
keywords: apis, graph api, supported apis, get, domain, related, devices
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
ms.openlocfilehash: 3fffb87c486e8b6b89b5e868b96d02dfae496e0b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166879"
---
# <a name="get-domain-related-machines-api"></a><span data-ttu-id="6e343-104">Получить API связанных с доменом машин</span><span class="sxs-lookup"><span data-stu-id="6e343-104">Get domain related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6e343-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6e343-105">**Applies to:**</span></span>
- [<span data-ttu-id="6e343-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6e343-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6e343-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e343-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6e343-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="6e343-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6e343-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="6e343-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="6e343-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="6e343-110">API description</span></span>
<span data-ttu-id="6e343-111">Извлекает коллекцию [машин,](machine.md) которые связывались с заданным доменным адресом или с него.</span><span class="sxs-lookup"><span data-stu-id="6e343-111">Retrieves a collection of [Machines](machine.md) that have communicated to or from a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="6e343-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6e343-112">Limitations</span></span>
1. <span data-ttu-id="6e343-113">Вы можете запрашивать на устройствах последнее обновление в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="6e343-113">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="6e343-114">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="6e343-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="6e343-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="6e343-115">Permissions</span></span>
<span data-ttu-id="6e343-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="6e343-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6e343-117">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6e343-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="6e343-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="6e343-118">Permission type</span></span> |   <span data-ttu-id="6e343-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="6e343-119">Permission</span></span>  |   <span data-ttu-id="6e343-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="6e343-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6e343-121">Приложение</span><span class="sxs-lookup"><span data-stu-id="6e343-121">Application</span></span> |   <span data-ttu-id="6e343-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="6e343-122">Machine.Read.All</span></span> |  <span data-ttu-id="6e343-123">'Read all machine profiles'</span><span class="sxs-lookup"><span data-stu-id="6e343-123">'Read all machine profiles'</span></span>
<span data-ttu-id="6e343-124">Приложение</span><span class="sxs-lookup"><span data-stu-id="6e343-124">Application</span></span> |   <span data-ttu-id="6e343-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="6e343-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="6e343-126">'Read and write all machine information'</span><span class="sxs-lookup"><span data-stu-id="6e343-126">'Read and write all machine information'</span></span>
<span data-ttu-id="6e343-127">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="6e343-127">Delegated (work or school account)</span></span> | <span data-ttu-id="6e343-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="6e343-128">Machine.Read</span></span> | <span data-ttu-id="6e343-129">'Read machine information'</span><span class="sxs-lookup"><span data-stu-id="6e343-129">'Read machine information'</span></span>
<span data-ttu-id="6e343-130">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="6e343-130">Delegated (work or school account)</span></span> | <span data-ttu-id="6e343-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6e343-131">Machine.ReadWrite</span></span> | <span data-ttu-id="6e343-132">'Read and write machine information'</span><span class="sxs-lookup"><span data-stu-id="6e343-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="6e343-133">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="6e343-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="6e343-134">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="6e343-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="6e343-135">Ответ будет включать только устройства, к которые пользователь может получить доступ на основе параметров группы устройств (см. статью Создание и управление [группами](machine-groups.md) устройств для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="6e343-135">Response will include only devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="6e343-136">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="6e343-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a><span data-ttu-id="6e343-137">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="6e343-137">Request headers</span></span>

<span data-ttu-id="6e343-138">Имя</span><span class="sxs-lookup"><span data-stu-id="6e343-138">Name</span></span> | <span data-ttu-id="6e343-139">Тип</span><span class="sxs-lookup"><span data-stu-id="6e343-139">Type</span></span> | <span data-ttu-id="6e343-140">Описание</span><span class="sxs-lookup"><span data-stu-id="6e343-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="6e343-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="6e343-141">Authorization</span></span> | <span data-ttu-id="6e343-142">Строка</span><span class="sxs-lookup"><span data-stu-id="6e343-142">String</span></span> | <span data-ttu-id="6e343-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6e343-143">Bearer {token}.</span></span> <span data-ttu-id="6e343-144">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="6e343-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6e343-145">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="6e343-145">Request body</span></span>
<span data-ttu-id="6e343-146">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="6e343-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6e343-147">Отклик</span><span class="sxs-lookup"><span data-stu-id="6e343-147">Response</span></span>
<span data-ttu-id="6e343-148">При успешном и доменном доступе — 200 ОК со списком [машинных](machine.md) сущностями.</span><span class="sxs-lookup"><span data-stu-id="6e343-148">If successful and domain exists - 200 OK with list of [machine](machine.md) entities.</span></span> <span data-ttu-id="6e343-149">Если домена не существует - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="6e343-149">If domain do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="6e343-150">Пример</span><span class="sxs-lookup"><span data-stu-id="6e343-150">Example</span></span>

<span data-ttu-id="6e343-151">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="6e343-151">**Request**</span></span>

<span data-ttu-id="6e343-152">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="6e343-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
