---
title: Получите API коллекции групп машин RBAC
description: Узнайте, как использовать API коллекции Get KB для получения коллекции групп устройств RBAC в Microsoft Defender Advanced Threat Protection.
keywords: apis, graph api, supported apis, get, RBAC, group
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/07/2018
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167023"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="a4b23-104">Получить API коллекции KB</span><span class="sxs-lookup"><span data-stu-id="a4b23-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a4b23-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a4b23-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="a4b23-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a4b23-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a4b23-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="a4b23-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="a4b23-108">Извлекает коллекцию групп устройств RBAC.</span><span class="sxs-lookup"><span data-stu-id="a4b23-108">Retrieves a collection of RBAC device groups.</span></span>

## <a name="permissions"></a><span data-ttu-id="a4b23-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="a4b23-109">Permissions</span></span>
<span data-ttu-id="a4b23-110">Пользователю нужны разрешения на чтение.</span><span class="sxs-lookup"><span data-stu-id="a4b23-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="a4b23-111">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="a4b23-111">HTTP request</span></span>
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a><span data-ttu-id="a4b23-112">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="a4b23-112">Request headers</span></span>

<span data-ttu-id="a4b23-113">Заголовок</span><span class="sxs-lookup"><span data-stu-id="a4b23-113">Header</span></span> | <span data-ttu-id="a4b23-114">Значение</span><span class="sxs-lookup"><span data-stu-id="a4b23-114">Value</span></span> 
:---|:---
<span data-ttu-id="a4b23-115">Авторизация</span><span class="sxs-lookup"><span data-stu-id="a4b23-115">Authorization</span></span> | <span data-ttu-id="a4b23-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a4b23-116">Bearer {token}.</span></span> <span data-ttu-id="a4b23-117">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="a4b23-117">**Required**.</span></span>
<span data-ttu-id="a4b23-118">Тип контента</span><span class="sxs-lookup"><span data-stu-id="a4b23-118">Content type</span></span> | <span data-ttu-id="a4b23-119">application/json</span><span class="sxs-lookup"><span data-stu-id="a4b23-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="a4b23-120">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="a4b23-120">Request body</span></span>
<span data-ttu-id="a4b23-121">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="a4b23-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a4b23-122">Отклик</span><span class="sxs-lookup"><span data-stu-id="a4b23-122">Response</span></span>
<span data-ttu-id="a4b23-123">Если успешно - 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="a4b23-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="a4b23-124">Пример</span><span class="sxs-lookup"><span data-stu-id="a4b23-124">Example</span></span>

<span data-ttu-id="a4b23-125">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="a4b23-125">**Request**</span></span>

<span data-ttu-id="a4b23-126">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="a4b23-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

<span data-ttu-id="a4b23-127">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="a4b23-127">**Response**</span></span>

<span data-ttu-id="a4b23-128">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="a4b23-128">Here is an example of the response.</span></span>
<span data-ttu-id="a4b23-129">Полевой id содержит **id** группы устройств и равен **полевой rbacGroupId** в сведениях о устройствах.</span><span class="sxs-lookup"><span data-stu-id="a4b23-129">Field id contains device group **id** and equal to field **rbacGroupId** in devices info.</span></span> <span data-ttu-id="a4b23-130">**Негруппировка** поля относится только к одной группе для всех устройств, которые не были назначены какой-либо группе.</span><span class="sxs-lookup"><span data-stu-id="a4b23-130">Field **ungrouped** is true only for one group for all devices that have not been assigned to any group.</span></span> <span data-ttu-id="a4b23-131">Эта группа, как обычно, имеет имя UnassignedGroup.</span><span class="sxs-lookup"><span data-stu-id="a4b23-131">This group as usual has name "UnassignedGroup".</span></span>

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
