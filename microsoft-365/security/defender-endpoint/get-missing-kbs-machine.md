---
title: Отсутствие KBs по ID устройства
description: Извлечение отсутствующих обновлений безопасности по ID устройства
keywords: apis, api graph, supported apis, get, list, file, information, device id, threat & vulnerability management api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 908ddf531a5a20b9811084ba534a152ad6158170
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198853"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="25e0f-104">Отсутствие KBs по ID устройства</span><span class="sxs-lookup"><span data-stu-id="25e0f-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="25e0f-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="25e0f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="25e0f-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="25e0f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="25e0f-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="25e0f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="25e0f-108">Извлечение отсутствующих КБ (обновлений безопасности) по ID устройства</span><span class="sxs-lookup"><span data-stu-id="25e0f-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="25e0f-109">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="25e0f-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="25e0f-110">Заготвка запроса</span><span class="sxs-lookup"><span data-stu-id="25e0f-110">Request header</span></span>

<span data-ttu-id="25e0f-111">Имя</span><span class="sxs-lookup"><span data-stu-id="25e0f-111">Name</span></span> | <span data-ttu-id="25e0f-112">Тип</span><span class="sxs-lookup"><span data-stu-id="25e0f-112">Type</span></span> | <span data-ttu-id="25e0f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="25e0f-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="25e0f-114">Авторизация</span><span class="sxs-lookup"><span data-stu-id="25e0f-114">Authorization</span></span> | <span data-ttu-id="25e0f-115">Строка</span><span class="sxs-lookup"><span data-stu-id="25e0f-115">String</span></span> | <span data-ttu-id="25e0f-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="25e0f-116">Bearer {token}.</span></span> <span data-ttu-id="25e0f-117">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="25e0f-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="25e0f-118">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="25e0f-118">Request body</span></span>

<span data-ttu-id="25e0f-119">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="25e0f-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="25e0f-120">Отклик</span><span class="sxs-lookup"><span data-stu-id="25e0f-120">Response</span></span>

<span data-ttu-id="25e0f-121">В случае успешной работы этот метод возвращает 200 ОК, при этом указанному устройству отсутствуют данные kb в теле.</span><span class="sxs-lookup"><span data-stu-id="25e0f-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="25e0f-122">Пример</span><span class="sxs-lookup"><span data-stu-id="25e0f-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="25e0f-123">Запрос</span><span class="sxs-lookup"><span data-stu-id="25e0f-123">Request</span></span>

<span data-ttu-id="25e0f-124">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="25e0f-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="25e0f-125">Отклик</span><span class="sxs-lookup"><span data-stu-id="25e0f-125">Response</span></span>

<span data-ttu-id="25e0f-126">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="25e0f-126">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="25e0f-127">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="25e0f-127">Related topics</span></span>

- [<span data-ttu-id="25e0f-128">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="25e0f-128">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="25e0f-129">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="25e0f-129">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
