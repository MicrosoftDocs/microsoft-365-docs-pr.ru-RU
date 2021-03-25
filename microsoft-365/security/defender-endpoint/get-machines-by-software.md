---
title: Список устройств по программному обеспечению
description: Извлечение списка устройств, на которые установлено это программное обеспечение.
keywords: apis, graph api, supported apis, get, list devices, devices list, list devices by software, mdatp tvm api
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
ms.openlocfilehash: 78cccee6380f0c403aab21eac4f07b64b8f8d510
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200393"
---
# <a name="list-devices-by-software"></a><span data-ttu-id="a9e4c-104">Список устройств по программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="a9e4c-104">List devices by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a9e4c-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a9e4c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="a9e4c-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a9e4c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a9e4c-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="a9e4c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="a9e4c-108">Извлечение списка ссылок на устройства с установленным программным обеспечением.</span><span class="sxs-lookup"><span data-stu-id="a9e4c-108">Retrieve a list of device references that has this software installed.</span></span>

## <a name="permissions"></a><span data-ttu-id="a9e4c-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="a9e4c-109">Permissions</span></span>
<span data-ttu-id="a9e4c-110">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="a9e4c-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a9e4c-111">Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a9e4c-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="a9e4c-112">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="a9e4c-112">Permission type</span></span> |   <span data-ttu-id="a9e4c-113">Разрешение</span><span class="sxs-lookup"><span data-stu-id="a9e4c-113">Permission</span></span>  |   <span data-ttu-id="a9e4c-114">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="a9e4c-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a9e4c-115">Application</span><span class="sxs-lookup"><span data-stu-id="a9e4c-115">Application</span></span> | <span data-ttu-id="a9e4c-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="a9e4c-116">Software.Read.All</span></span> | <span data-ttu-id="a9e4c-117">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="a9e4c-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="a9e4c-118">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="a9e4c-118">Delegated (work or school account)</span></span> | <span data-ttu-id="a9e4c-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="a9e4c-119">Software.Read</span></span> | <span data-ttu-id="a9e4c-120">'Read Threat and Vulnerability Management Software information'</span><span class="sxs-lookup"><span data-stu-id="a9e4c-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="a9e4c-121">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="a9e4c-121">HTTP request</span></span>
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a><span data-ttu-id="a9e4c-122">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="a9e4c-122">Request headers</span></span>

| <span data-ttu-id="a9e4c-123">Имя</span><span class="sxs-lookup"><span data-stu-id="a9e4c-123">Name</span></span>        | <span data-ttu-id="a9e4c-124">Тип</span><span class="sxs-lookup"><span data-stu-id="a9e4c-124">Type</span></span> | <span data-ttu-id="a9e4c-125">Описание</span><span class="sxs-lookup"><span data-stu-id="a9e4c-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="a9e4c-126">Авторизация</span><span class="sxs-lookup"><span data-stu-id="a9e4c-126">Authorization</span></span> | <span data-ttu-id="a9e4c-127">Строка</span><span class="sxs-lookup"><span data-stu-id="a9e4c-127">String</span></span> | <span data-ttu-id="a9e4c-128">Bearer {token}. **Обязательно**.</span><span class="sxs-lookup"><span data-stu-id="a9e4c-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a9e4c-129">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="a9e4c-129">Request body</span></span>
<span data-ttu-id="a9e4c-130">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="a9e4c-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a9e4c-131">Отклик</span><span class="sxs-lookup"><span data-stu-id="a9e4c-131">Response</span></span>
<span data-ttu-id="a9e4c-132">В случае успеха этот метод возвращает 200 ОК и список устройств с программным обеспечением, установленным в теле.</span><span class="sxs-lookup"><span data-stu-id="a9e4c-132">If successful, this method returns 200 OK and a list of devices with the software installed in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="a9e4c-133">Пример</span><span class="sxs-lookup"><span data-stu-id="a9e4c-133">Example</span></span>

<span data-ttu-id="a9e4c-134">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="a9e4c-134">**Request**</span></span>

<span data-ttu-id="a9e4c-135">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="a9e4c-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

<span data-ttu-id="a9e4c-136">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="a9e4c-136">**Response**</span></span>

<span data-ttu-id="a9e4c-137">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="a9e4c-137">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="a9e4c-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a9e4c-138">Related topics</span></span>
- [<span data-ttu-id="a9e4c-139">Управление рисками & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="a9e4c-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="a9e4c-140">Инвентаризация программного обеспечения & уязвимости</span><span class="sxs-lookup"><span data-stu-id="a9e4c-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
