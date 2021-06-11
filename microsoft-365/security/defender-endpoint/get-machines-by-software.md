---
title: Список устройств по программному обеспечению
description: Извлечение списка устройств, на которые установлено это программное обеспечение.
keywords: apis, graph api, supported apis, get, list devices, devices list devices by software, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8312818fe06b5a25ae32bf1f9585a51fe8848de6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845382"
---
# <a name="list-devices-by-software"></a><span data-ttu-id="0acdf-104">Список устройств по программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="0acdf-104">List devices by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0acdf-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0acdf-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="0acdf-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="0acdf-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0acdf-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="0acdf-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="0acdf-108">Извлечение списка ссылок на устройства с установленным программным обеспечением.</span><span class="sxs-lookup"><span data-stu-id="0acdf-108">Retrieve a list of device references that has this software installed.</span></span>

## <a name="permissions"></a><span data-ttu-id="0acdf-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="0acdf-109">Permissions</span></span>
<span data-ttu-id="0acdf-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="0acdf-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0acdf-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0acdf-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="0acdf-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="0acdf-112">Permission type</span></span> |   <span data-ttu-id="0acdf-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="0acdf-113">Permission</span></span>  |   <span data-ttu-id="0acdf-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="0acdf-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0acdf-115">Приложение</span><span class="sxs-lookup"><span data-stu-id="0acdf-115">Application</span></span> | <span data-ttu-id="0acdf-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="0acdf-116">Software.Read.All</span></span> | <span data-ttu-id="0acdf-117">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="0acdf-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="0acdf-118">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="0acdf-118">Delegated (work or school account)</span></span> | <span data-ttu-id="0acdf-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="0acdf-119">Software.Read</span></span> | <span data-ttu-id="0acdf-120">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="0acdf-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="0acdf-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="0acdf-121">HTTP request</span></span>
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a><span data-ttu-id="0acdf-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="0acdf-122">Request headers</span></span>

| <span data-ttu-id="0acdf-123">Имя</span><span class="sxs-lookup"><span data-stu-id="0acdf-123">Name</span></span>        | <span data-ttu-id="0acdf-124">Тип</span><span class="sxs-lookup"><span data-stu-id="0acdf-124">Type</span></span> | <span data-ttu-id="0acdf-125">Описание</span><span class="sxs-lookup"><span data-stu-id="0acdf-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="0acdf-126">Авторизация</span><span class="sxs-lookup"><span data-stu-id="0acdf-126">Authorization</span></span> | <span data-ttu-id="0acdf-127">String</span><span class="sxs-lookup"><span data-stu-id="0acdf-127">String</span></span> | <span data-ttu-id="0acdf-128">Bearer {token}. **Обязательно**.</span><span class="sxs-lookup"><span data-stu-id="0acdf-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="0acdf-129">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="0acdf-129">Request body</span></span>
<span data-ttu-id="0acdf-130">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="0acdf-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0acdf-131">Отклик</span><span class="sxs-lookup"><span data-stu-id="0acdf-131">Response</span></span>
<span data-ttu-id="0acdf-132">В случае успеха этот метод возвращает 200 ОК и список устройств с программным обеспечением, установленным в теле.</span><span class="sxs-lookup"><span data-stu-id="0acdf-132">If successful, this method returns 200 OK and a list of devices with the software installed in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="0acdf-133">Пример</span><span class="sxs-lookup"><span data-stu-id="0acdf-133">Example</span></span>

<span data-ttu-id="0acdf-134">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="0acdf-134">**Request**</span></span>

<span data-ttu-id="0acdf-135">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="0acdf-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

<span data-ttu-id="0acdf-136">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="0acdf-136">**Response**</span></span>

<span data-ttu-id="0acdf-137">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="0acdf-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="0acdf-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0acdf-138">Related topics</span></span>
- [<span data-ttu-id="0acdf-139">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="0acdf-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="0acdf-140">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="0acdf-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
