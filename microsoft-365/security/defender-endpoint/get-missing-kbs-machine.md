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
ms.openlocfilehash: 63400295061cd7adc58a4ddebf73f4c82b0cc969
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845238"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="11375-104">Отсутствие KBs по ID устройства</span><span class="sxs-lookup"><span data-stu-id="11375-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="11375-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="11375-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="11375-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="11375-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="11375-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="11375-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="11375-108">Извлечение отсутствующих КБ (обновлений безопасности) по ID устройства</span><span class="sxs-lookup"><span data-stu-id="11375-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="11375-109">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="11375-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="11375-110">Заготвка запроса</span><span class="sxs-lookup"><span data-stu-id="11375-110">Request header</span></span>

<span data-ttu-id="11375-111">Имя</span><span class="sxs-lookup"><span data-stu-id="11375-111">Name</span></span> | <span data-ttu-id="11375-112">Тип</span><span class="sxs-lookup"><span data-stu-id="11375-112">Type</span></span> | <span data-ttu-id="11375-113">Описание</span><span class="sxs-lookup"><span data-stu-id="11375-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="11375-114">Authorization</span><span class="sxs-lookup"><span data-stu-id="11375-114">Authorization</span></span> | <span data-ttu-id="11375-115">String</span><span class="sxs-lookup"><span data-stu-id="11375-115">String</span></span> | <span data-ttu-id="11375-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="11375-116">Bearer {token}.</span></span> <span data-ttu-id="11375-117">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="11375-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="11375-118">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="11375-118">Request body</span></span>

<span data-ttu-id="11375-119">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="11375-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="11375-120">Отклик</span><span class="sxs-lookup"><span data-stu-id="11375-120">Response</span></span>

<span data-ttu-id="11375-121">В случае успешной работы этот метод возвращает 200 ОК, при этом указанному устройству отсутствуют данные kb в теле.</span><span class="sxs-lookup"><span data-stu-id="11375-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="11375-122">Пример</span><span class="sxs-lookup"><span data-stu-id="11375-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="11375-123">Запрос</span><span class="sxs-lookup"><span data-stu-id="11375-123">Request</span></span>

<span data-ttu-id="11375-124">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="11375-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="11375-125">Отклик</span><span class="sxs-lookup"><span data-stu-id="11375-125">Response</span></span>

<span data-ttu-id="11375-126">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="11375-126">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="11375-127">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="11375-127">Related topics</span></span>

- [<span data-ttu-id="11375-128">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="11375-128">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="11375-129">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="11375-129">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
