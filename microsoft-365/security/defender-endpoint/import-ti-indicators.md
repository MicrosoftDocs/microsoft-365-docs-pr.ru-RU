---
title: API индикаторов импорта
description: Узнайте, как использовать импортную партию API индикатора в Microsoft Defender для конечной точки.
keywords: apis, поддерживаемые apis, отправка, ti, индикатор, обновление
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
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198249"
---
# <a name="import-indicators-api"></a><span data-ttu-id="75f85-104">API индикаторов импорта</span><span class="sxs-lookup"><span data-stu-id="75f85-104">Import Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="75f85-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="75f85-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="75f85-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="75f85-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="75f85-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="75f85-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="75f85-108">Описание API</span><span class="sxs-lookup"><span data-stu-id="75f85-108">API description</span></span>
<span data-ttu-id="75f85-109">Отправка или обновление пакета [сущностями индикатора.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="75f85-109">Submits or Updates batch of [Indicator](ti-indicator.md) entities.</span></span>
<br><span data-ttu-id="75f85-110">Нотация CIDR для ИП не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="75f85-110">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="75f85-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="75f85-111">Limitations</span></span>
1. <span data-ttu-id="75f85-112">Ограничения скорости для этого API — 30 вызовов в минуту.</span><span class="sxs-lookup"><span data-stu-id="75f85-112">Rate limitations for this API are 30 calls per minute.</span></span>
2. <span data-ttu-id="75f85-113">Существует ограничение в 15 000 активных [индикаторов на](ti-indicator.md) одного клиента.</span><span class="sxs-lookup"><span data-stu-id="75f85-113">There is a limit of 15,000 active [Indicators](ti-indicator.md) per tenant.</span></span> 
3. <span data-ttu-id="75f85-114">Максимальный размер пакета для одного вызова API — 500.</span><span class="sxs-lookup"><span data-stu-id="75f85-114">Maximum batch size for one API call is 500.</span></span>

## <a name="permissions"></a><span data-ttu-id="75f85-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="75f85-115">Permissions</span></span>
<span data-ttu-id="75f85-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="75f85-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="75f85-117">Дополнительные новости, в том числе выбор разрешений, см. в [руб. Начало работы](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="75f85-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="75f85-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="75f85-118">Permission type</span></span> |   <span data-ttu-id="75f85-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="75f85-119">Permission</span></span>  |   <span data-ttu-id="75f85-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="75f85-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="75f85-121">Приложение</span><span class="sxs-lookup"><span data-stu-id="75f85-121">Application</span></span> |   <span data-ttu-id="75f85-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="75f85-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="75f85-123">'Read and write Indicators'</span><span class="sxs-lookup"><span data-stu-id="75f85-123">'Read and write Indicators'</span></span>
<span data-ttu-id="75f85-124">Приложение</span><span class="sxs-lookup"><span data-stu-id="75f85-124">Application</span></span> |   <span data-ttu-id="75f85-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="75f85-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="75f85-126">'Read and write All Indicators'</span><span class="sxs-lookup"><span data-stu-id="75f85-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="75f85-127">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="75f85-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="75f85-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="75f85-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="75f85-129">'Read and write Indicators'</span><span class="sxs-lookup"><span data-stu-id="75f85-129">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="75f85-130">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="75f85-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a><span data-ttu-id="75f85-131">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="75f85-131">Request headers</span></span>

<span data-ttu-id="75f85-132">Имя</span><span class="sxs-lookup"><span data-stu-id="75f85-132">Name</span></span> | <span data-ttu-id="75f85-133">Тип</span><span class="sxs-lookup"><span data-stu-id="75f85-133">Type</span></span> | <span data-ttu-id="75f85-134">Описание</span><span class="sxs-lookup"><span data-stu-id="75f85-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="75f85-135">Авторизация</span><span class="sxs-lookup"><span data-stu-id="75f85-135">Authorization</span></span> | <span data-ttu-id="75f85-136">String</span><span class="sxs-lookup"><span data-stu-id="75f85-136">String</span></span> | <span data-ttu-id="75f85-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="75f85-137">Bearer {token}.</span></span> <span data-ttu-id="75f85-138">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="75f85-138">**Required**.</span></span>
<span data-ttu-id="75f85-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="75f85-139">Content-Type</span></span> | <span data-ttu-id="75f85-140">string</span><span class="sxs-lookup"><span data-stu-id="75f85-140">string</span></span> | <span data-ttu-id="75f85-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="75f85-141">application/json.</span></span> <span data-ttu-id="75f85-142">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="75f85-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="75f85-143">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="75f85-143">Request body</span></span>
<span data-ttu-id="75f85-144">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="75f85-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="75f85-145">Параметр</span><span class="sxs-lookup"><span data-stu-id="75f85-145">Parameter</span></span> | <span data-ttu-id="75f85-146">Тип</span><span class="sxs-lookup"><span data-stu-id="75f85-146">Type</span></span>    | <span data-ttu-id="75f85-147">Описание</span><span class="sxs-lookup"><span data-stu-id="75f85-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="75f85-148">Индикаторы</span><span class="sxs-lookup"><span data-stu-id="75f85-148">Indicators</span></span> | <span data-ttu-id="75f85-149">Индикатор<[списка](ti-indicator.md)></span><span class="sxs-lookup"><span data-stu-id="75f85-149">List<[Indicator](ti-indicator.md)></span></span> | <span data-ttu-id="75f85-150">Список [индикаторов](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="75f85-150">List of [Indicators](ti-indicator.md).</span></span> <span data-ttu-id="75f85-151">**Required**</span><span class="sxs-lookup"><span data-stu-id="75f85-151">**Required**</span></span>


## <a name="response"></a><span data-ttu-id="75f85-152">Отклик</span><span class="sxs-lookup"><span data-stu-id="75f85-152">Response</span></span>
- <span data-ttu-id="75f85-153">В случае успешного результата этот метод возвращает код ответа 200 ОК со списком результатов импорта для каждого индикатора, см. в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="75f85-153">If successful, this method returns 200 - OK response code with a list of import results per indicator, see example below.</span></span>
- <span data-ttu-id="75f85-154">Если не удалось: этот метод возвращает 400 — Bad Request.</span><span class="sxs-lookup"><span data-stu-id="75f85-154">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="75f85-155">Плохой запрос обычно указывает неправильное тело.</span><span class="sxs-lookup"><span data-stu-id="75f85-155">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="75f85-156">Пример</span><span class="sxs-lookup"><span data-stu-id="75f85-156">Example</span></span>

<span data-ttu-id="75f85-157">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="75f85-157">**Request**</span></span>

<span data-ttu-id="75f85-158">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="75f85-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

<span data-ttu-id="75f85-159">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="75f85-159">**Response**</span></span>

<span data-ttu-id="75f85-160">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="75f85-160">Here is an example of the response.</span></span>

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="75f85-161">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="75f85-161">Related topic</span></span>
- [<span data-ttu-id="75f85-162">Управление индикаторами</span><span class="sxs-lookup"><span data-stu-id="75f85-162">Manage indicators</span></span>](manage-indicators.md)
