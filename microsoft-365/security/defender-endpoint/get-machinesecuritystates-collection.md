---
title: Получить API коллекций состояния безопасности компьютеров
description: Извлечение коллекции состояния безопасности устройств с помощью Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, device, security, state
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
ms.openlocfilehash: 9dab4bdccc1fead5bc2cc5b9bdff8f2a45b6c8db
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200369"
---
# <a name="get-machines-security-states-collection-api"></a><span data-ttu-id="b5720-104">API коллекций состояния безопасности Get Machines</span><span class="sxs-lookup"><span data-stu-id="b5720-104">Get Machines security states collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b5720-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b5720-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b5720-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b5720-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b5720-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b5720-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b5720-108">Извлекает коллекцию состояния безопасности устройств.</span><span class="sxs-lookup"><span data-stu-id="b5720-108">Retrieves a collection of devices security states.</span></span>

## <a name="permissions"></a><span data-ttu-id="b5720-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="b5720-109">Permissions</span></span>
<span data-ttu-id="b5720-110">Пользователю нужны разрешения на чтение.</span><span class="sxs-lookup"><span data-stu-id="b5720-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="b5720-111">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="b5720-111">HTTP request</span></span>
```
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a><span data-ttu-id="b5720-112">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="b5720-112">Request headers</span></span>

<span data-ttu-id="b5720-113">Заголовок</span><span class="sxs-lookup"><span data-stu-id="b5720-113">Header</span></span> | <span data-ttu-id="b5720-114">Значение</span><span class="sxs-lookup"><span data-stu-id="b5720-114">Value</span></span> 
:---|:---
<span data-ttu-id="b5720-115">Авторизация</span><span class="sxs-lookup"><span data-stu-id="b5720-115">Authorization</span></span> | <span data-ttu-id="b5720-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b5720-116">Bearer {token}.</span></span> <span data-ttu-id="b5720-117">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="b5720-117">**Required**.</span></span>
<span data-ttu-id="b5720-118">Тип контента</span><span class="sxs-lookup"><span data-stu-id="b5720-118">Content type</span></span> | <span data-ttu-id="b5720-119">application/json</span><span class="sxs-lookup"><span data-stu-id="b5720-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="b5720-120">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="b5720-120">Request body</span></span>
<span data-ttu-id="b5720-121">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="b5720-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b5720-122">Отклик</span><span class="sxs-lookup"><span data-stu-id="b5720-122">Response</span></span>
<span data-ttu-id="b5720-123">Если успешно - 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="b5720-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="b5720-124">Пример</span><span class="sxs-lookup"><span data-stu-id="b5720-124">Example</span></span>

<span data-ttu-id="b5720-125">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="b5720-125">**Request**</span></span>

<span data-ttu-id="b5720-126">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="b5720-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

<span data-ttu-id="b5720-127">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="b5720-127">**Response**</span></span>

<span data-ttu-id="b5720-128">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="b5720-128">Here is an example of the response.</span></span>
<span data-ttu-id="b5720-129">Полевой *id* содержит id устройства и равен полевой *id*\* в сведениях о устройствах.</span><span class="sxs-lookup"><span data-stu-id="b5720-129">Field *id* contains device id and equal to the field *id*\* in devices info.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        …
    ]
}
```
