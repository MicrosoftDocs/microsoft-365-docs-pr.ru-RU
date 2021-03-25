---
title: Поиск сведений о устройстве с помощью внутреннего API IP
description: Используйте этот API для создания вызовов, связанных с поиском записи устройства вокруг определенного времени с помощью внутреннего IP-адреса.
keywords: IP, apis, api graph, supported apis, find device, device information
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167143"
---
# <a name="find-device-information-by-internal-ip-api"></a><span data-ttu-id="b73be-104">Поиск сведений о устройстве с помощью внутреннего API IP</span><span class="sxs-lookup"><span data-stu-id="b73be-104">Find device information by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b73be-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b73be-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="b73be-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b73be-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b73be-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b73be-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b73be-108">Поиск устройства по внутреннему IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="b73be-108">Find a device by internal IP.</span></span>

>[!NOTE]
><span data-ttu-id="b73be-109">Время должно быть в течение последних 30 дней.</span><span class="sxs-lookup"><span data-stu-id="b73be-109">The timestamp must be within the last 30 days.</span></span>

## <a name="permissions"></a><span data-ttu-id="b73be-110">Разрешения</span><span class="sxs-lookup"><span data-stu-id="b73be-110">Permissions</span></span>
<span data-ttu-id="b73be-111">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="b73be-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b73be-112">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b73be-112">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b73be-113">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="b73be-113">Permission type</span></span> | <span data-ttu-id="b73be-114">Разрешение</span><span class="sxs-lookup"><span data-stu-id="b73be-114">Permission</span></span> | <span data-ttu-id="b73be-115">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="b73be-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b73be-116">Приложение</span><span class="sxs-lookup"><span data-stu-id="b73be-116">Application</span></span> | <span data-ttu-id="b73be-117">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="b73be-117">Machine.Read.All</span></span> | <span data-ttu-id="b73be-118">'Read all machine profiles'</span><span class="sxs-lookup"><span data-stu-id="b73be-118">'Read all machine profiles'</span></span>
<span data-ttu-id="b73be-119">Приложение</span><span class="sxs-lookup"><span data-stu-id="b73be-119">Application</span></span> | <span data-ttu-id="b73be-120">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b73be-120">Machine.ReadWrite.All</span></span> | <span data-ttu-id="b73be-121">'Read and write all machine information'</span><span class="sxs-lookup"><span data-stu-id="b73be-121">'Read and write all machine information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b73be-122">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="b73be-122">HTTP request</span></span>
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a><span data-ttu-id="b73be-123">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="b73be-123">Request headers</span></span>

<span data-ttu-id="b73be-124">Имя</span><span class="sxs-lookup"><span data-stu-id="b73be-124">Name</span></span> | <span data-ttu-id="b73be-125">Тип</span><span class="sxs-lookup"><span data-stu-id="b73be-125">Type</span></span> | <span data-ttu-id="b73be-126">Описание</span><span class="sxs-lookup"><span data-stu-id="b73be-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="b73be-127">Authorization</span><span class="sxs-lookup"><span data-stu-id="b73be-127">Authorization</span></span> | <span data-ttu-id="b73be-128">Строка</span><span class="sxs-lookup"><span data-stu-id="b73be-128">String</span></span> | <span data-ttu-id="b73be-129">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b73be-129">Bearer {token}.</span></span> <span data-ttu-id="b73be-130">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="b73be-130">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b73be-131">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="b73be-131">Request body</span></span>
<span data-ttu-id="b73be-132">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="b73be-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b73be-133">Отклик</span><span class="sxs-lookup"><span data-stu-id="b73be-133">Response</span></span>
<span data-ttu-id="b73be-134">Если успешно и машина существует - 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="b73be-134">If successful and machine exists - 200 OK.</span></span>
<span data-ttu-id="b73be-135">Если машина не найдена - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="b73be-135">If no machine found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="b73be-136">Пример</span><span class="sxs-lookup"><span data-stu-id="b73be-136">Example</span></span>

<span data-ttu-id="b73be-137">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="b73be-137">**Request**</span></span>

<span data-ttu-id="b73be-138">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="b73be-138">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

<span data-ttu-id="b73be-139">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="b73be-139">**Response**</span></span>

<span data-ttu-id="b73be-140">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="b73be-140">Here is an example of the response.</span></span>

<span data-ttu-id="b73be-141">Ответ возвращает список всех устройств, которые сообщили об этом IP-адресе в течение шестнадцати минут до и после времени.</span><span class="sxs-lookup"><span data-stu-id="b73be-141">The response will return a list of all devices that reported this IP address within sixteen minutes prior and after the timestamp.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
