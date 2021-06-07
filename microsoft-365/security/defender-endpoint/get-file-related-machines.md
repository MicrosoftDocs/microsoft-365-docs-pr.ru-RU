---
title: Получить API машин, связанных с файлами
description: Узнайте, как использовать API машин Get, связанных с файлами, чтобы получить коллекцию машин, связанных с hash файла в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, devices, hash
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
ms.openlocfilehash: 211a29bcd9265ae20c4f3e1817fcaaf562260d39
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770281"
---
# <a name="get-file-related-machines-api"></a><span data-ttu-id="c8295-104">Получить API машин, связанных с файлами</span><span class="sxs-lookup"><span data-stu-id="c8295-104">Get file-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c8295-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c8295-105">**Applies to:**</span></span>
- [<span data-ttu-id="c8295-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c8295-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c8295-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8295-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c8295-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c8295-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c8295-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c8295-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c8295-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="c8295-110">API description</span></span>
<span data-ttu-id="c8295-111">Извлекает коллекцию [машин, связанных](machine.md) с данными файлами.</span><span class="sxs-lookup"><span data-stu-id="c8295-111">Retrieves a collection of [Machines](machine.md) related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="c8295-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c8295-112">Limitations</span></span>
1. <span data-ttu-id="c8295-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="c8295-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="c8295-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="c8295-114">Permissions</span></span>
<span data-ttu-id="c8295-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="c8295-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c8295-116">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c8295-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c8295-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="c8295-117">Permission type</span></span> |   <span data-ttu-id="c8295-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="c8295-118">Permission</span></span>  |   <span data-ttu-id="c8295-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="c8295-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c8295-120">Приложение</span><span class="sxs-lookup"><span data-stu-id="c8295-120">Application</span></span> |   <span data-ttu-id="c8295-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="c8295-121">Machine.Read.All</span></span> |  <span data-ttu-id="c8295-122">'Read all machine profiles'</span><span class="sxs-lookup"><span data-stu-id="c8295-122">'Read all machine profiles'</span></span>
<span data-ttu-id="c8295-123">Приложение</span><span class="sxs-lookup"><span data-stu-id="c8295-123">Application</span></span> |   <span data-ttu-id="c8295-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c8295-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="c8295-125">'Read and write all machine information'</span><span class="sxs-lookup"><span data-stu-id="c8295-125">'Read and write all machine information'</span></span>
<span data-ttu-id="c8295-126">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="c8295-126">Delegated (work or school account)</span></span> | <span data-ttu-id="c8295-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="c8295-127">Machine.Read</span></span> | <span data-ttu-id="c8295-128">'Read machine information'</span><span class="sxs-lookup"><span data-stu-id="c8295-128">'Read machine information'</span></span>
<span data-ttu-id="c8295-129">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="c8295-129">Delegated (work or school account)</span></span> | <span data-ttu-id="c8295-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c8295-130">Machine.ReadWrite</span></span> | <span data-ttu-id="c8295-131">'Read and write machine information'</span><span class="sxs-lookup"><span data-stu-id="c8295-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="c8295-132">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="c8295-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c8295-133">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="c8295-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="c8295-134">Ответ будет включать только устройства, к которые пользователь имеет доступ на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="c8295-134">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c8295-135">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="c8295-135">HTTP request</span></span>
```
GET /api/files/{id}/machines
```

## <a name="request-headers"></a><span data-ttu-id="c8295-136">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="c8295-136">Request headers</span></span>

<span data-ttu-id="c8295-137">Имя</span><span class="sxs-lookup"><span data-stu-id="c8295-137">Name</span></span> | <span data-ttu-id="c8295-138">Тип</span><span class="sxs-lookup"><span data-stu-id="c8295-138">Type</span></span> | <span data-ttu-id="c8295-139">Описание</span><span class="sxs-lookup"><span data-stu-id="c8295-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="c8295-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="c8295-140">Authorization</span></span> | <span data-ttu-id="c8295-141">String</span><span class="sxs-lookup"><span data-stu-id="c8295-141">String</span></span> | <span data-ttu-id="c8295-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c8295-142">Bearer {token}.</span></span> <span data-ttu-id="c8295-143">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="c8295-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="c8295-144">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="c8295-144">Request body</span></span>
<span data-ttu-id="c8295-145">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="c8295-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c8295-146">Отклик</span><span class="sxs-lookup"><span data-stu-id="c8295-146">Response</span></span>
<span data-ttu-id="c8295-147">При успешном и файле существует — [](machine.md) 200 ОК со списком машинных сущностями в теле.</span><span class="sxs-lookup"><span data-stu-id="c8295-147">If successful and file exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="c8295-148">Если файл не существует - 404 Не найден.</span><span class="sxs-lookup"><span data-stu-id="c8295-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="c8295-149">Пример</span><span class="sxs-lookup"><span data-stu-id="c8295-149">Example</span></span>

<span data-ttu-id="c8295-150">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="c8295-150">**Request**</span></span>

<span data-ttu-id="c8295-151">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="c8295-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/machines
```
