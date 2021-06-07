---
title: Отсутствие KBs по ID устройства
description: Извлечение отсутствующих обновлений безопасности по ID устройства
keywords: apis, graph api, supported apis, get, list, file, information, device id, threat & управление уязвимостями api, Microsoft Defender for Endpoint tvm api
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 97cad51938c4ff3498234dbf2e9d69fd48a52367
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771877"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="515cc-104">Отсутствие KBs по ID устройства</span><span class="sxs-lookup"><span data-stu-id="515cc-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="515cc-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="515cc-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="515cc-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="515cc-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="515cc-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="515cc-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="515cc-108">Извлечение отсутствующих КБ (обновлений безопасности) по ID устройства</span><span class="sxs-lookup"><span data-stu-id="515cc-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="515cc-109">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="515cc-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="515cc-110">Заготвка запроса</span><span class="sxs-lookup"><span data-stu-id="515cc-110">Request header</span></span>

<span data-ttu-id="515cc-111">Имя</span><span class="sxs-lookup"><span data-stu-id="515cc-111">Name</span></span> | <span data-ttu-id="515cc-112">Тип</span><span class="sxs-lookup"><span data-stu-id="515cc-112">Type</span></span> | <span data-ttu-id="515cc-113">Описание</span><span class="sxs-lookup"><span data-stu-id="515cc-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="515cc-114">Authorization</span><span class="sxs-lookup"><span data-stu-id="515cc-114">Authorization</span></span> | <span data-ttu-id="515cc-115">String</span><span class="sxs-lookup"><span data-stu-id="515cc-115">String</span></span> | <span data-ttu-id="515cc-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="515cc-116">Bearer {token}.</span></span> <span data-ttu-id="515cc-117">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="515cc-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="515cc-118">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="515cc-118">Request body</span></span>

<span data-ttu-id="515cc-119">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="515cc-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="515cc-120">Отклик</span><span class="sxs-lookup"><span data-stu-id="515cc-120">Response</span></span>

<span data-ttu-id="515cc-121">В случае успешной работы этот метод возвращает 200 ОК, при этом указанному устройству отсутствуют данные kb в теле.</span><span class="sxs-lookup"><span data-stu-id="515cc-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="515cc-122">Пример</span><span class="sxs-lookup"><span data-stu-id="515cc-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="515cc-123">Запрос</span><span class="sxs-lookup"><span data-stu-id="515cc-123">Request</span></span>

<span data-ttu-id="515cc-124">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="515cc-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="515cc-125">Отклик</span><span class="sxs-lookup"><span data-stu-id="515cc-125">Response</span></span>

<span data-ttu-id="515cc-126">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="515cc-126">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="515cc-127">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="515cc-127">Related topics</span></span>

- [<span data-ttu-id="515cc-128">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="515cc-128">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="515cc-129">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="515cc-129">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
