---
title: Отсутствие KBs по ID устройства
description: Извлечение отсутствующих обновлений безопасности по ID устройства
keywords: apis, graph api, supported apis, get, list, file, information, device id, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: aa22b90b95788d9f5a65d54c7a335a2e0f4c3091
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933581"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="4b550-104">Отсутствие KBs по ID устройства</span><span class="sxs-lookup"><span data-stu-id="4b550-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4b550-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4b550-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="4b550-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="4b550-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4b550-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="4b550-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="4b550-108">Извлечение отсутствующих КБ (обновлений безопасности) по ID устройства</span><span class="sxs-lookup"><span data-stu-id="4b550-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="4b550-109">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="4b550-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="4b550-110">Заготвка запроса</span><span class="sxs-lookup"><span data-stu-id="4b550-110">Request header</span></span>

<span data-ttu-id="4b550-111">Имя</span><span class="sxs-lookup"><span data-stu-id="4b550-111">Name</span></span> | <span data-ttu-id="4b550-112">Тип</span><span class="sxs-lookup"><span data-stu-id="4b550-112">Type</span></span> | <span data-ttu-id="4b550-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4b550-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="4b550-114">Authorization</span><span class="sxs-lookup"><span data-stu-id="4b550-114">Authorization</span></span> | <span data-ttu-id="4b550-115">String</span><span class="sxs-lookup"><span data-stu-id="4b550-115">String</span></span> | <span data-ttu-id="4b550-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4b550-116">Bearer {token}.</span></span> <span data-ttu-id="4b550-117">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="4b550-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="4b550-118">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="4b550-118">Request body</span></span>

<span data-ttu-id="4b550-119">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="4b550-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4b550-120">Отклик</span><span class="sxs-lookup"><span data-stu-id="4b550-120">Response</span></span>

<span data-ttu-id="4b550-121">В случае успешной работы этот метод возвращает 200 ОК, при этом указанному устройству отсутствуют данные kb в теле.</span><span class="sxs-lookup"><span data-stu-id="4b550-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="4b550-122">Пример</span><span class="sxs-lookup"><span data-stu-id="4b550-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="4b550-123">Запрос</span><span class="sxs-lookup"><span data-stu-id="4b550-123">Request</span></span>

<span data-ttu-id="4b550-124">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="4b550-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="4b550-125">Отклик</span><span class="sxs-lookup"><span data-stu-id="4b550-125">Response</span></span>

<span data-ttu-id="4b550-126">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="4b550-126">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="4b550-127">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="4b550-127">Related topics</span></span>

- [<span data-ttu-id="4b550-128">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="4b550-128">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="4b550-129">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="4b550-129">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
