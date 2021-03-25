---
title: Программный интерфейс расширенной охоты
ms.reviewer: ''
description: Узнайте, как использовать расширенный API охоты для запуска расширенных запросов в Microsoft Defender для конечной точки. Узнайте об ограничениях и см. пример.
keywords: apis, поддерживаемый apis, расширенный поиск, запрос
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: caf7a1bacfd726c560356d542bec3cf56c6b39d4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200201"
---
# <a name="advanced-hunting-api"></a><span data-ttu-id="36fd2-105">Расширенный API охоты</span><span class="sxs-lookup"><span data-stu-id="36fd2-105">Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="36fd2-106">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="36fd2-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="36fd2-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="36fd2-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="36fd2-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="36fd2-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a><span data-ttu-id="36fd2-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="36fd2-109">Limitations</span></span>
1. <span data-ttu-id="36fd2-110">Запрос по данным можно выполнить только за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="36fd2-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="36fd2-111">Результаты будут включать не более 100 000 строк.</span><span class="sxs-lookup"><span data-stu-id="36fd2-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="36fd2-112">Количество исполняемой работы ограничено для каждого клиента:</span><span class="sxs-lookup"><span data-stu-id="36fd2-112">The number of executions is limited per tenant:</span></span>
   - <span data-ttu-id="36fd2-113">Вызовы API: до 45 вызовов в минуту.</span><span class="sxs-lookup"><span data-stu-id="36fd2-113">API calls: Up to 45 calls per minute.</span></span>
   - <span data-ttu-id="36fd2-114">Время выполнения: 10 минут времени работы каждый час и 3 часа в день.</span><span class="sxs-lookup"><span data-stu-id="36fd2-114">Execution time: 10 minutes of running time every hour and 3 hours of running time a day.</span></span>
4. <span data-ttu-id="36fd2-115">Максимальное время выполнения одного запроса — 10 минут.</span><span class="sxs-lookup"><span data-stu-id="36fd2-115">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="36fd2-116">Ответ 429 будет представлять достижение ограничения квоты по количеству запросов или по ЦП.</span><span class="sxs-lookup"><span data-stu-id="36fd2-116">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="36fd2-117">Прочитайте текст ответа, чтобы понять, какой предел был достигнут.</span><span class="sxs-lookup"><span data-stu-id="36fd2-117">Read response body to understand what limit has been reached.</span></span> 

## <a name="permissions"></a><span data-ttu-id="36fd2-118">Разрешения</span><span class="sxs-lookup"><span data-stu-id="36fd2-118">Permissions</span></span>
<span data-ttu-id="36fd2-119">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="36fd2-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="36fd2-120">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="36fd2-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="36fd2-121">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="36fd2-121">Permission type</span></span> |   <span data-ttu-id="36fd2-122">Разрешение</span><span class="sxs-lookup"><span data-stu-id="36fd2-122">Permission</span></span>  |   <span data-ttu-id="36fd2-123">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="36fd2-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="36fd2-124">Application</span><span class="sxs-lookup"><span data-stu-id="36fd2-124">Application</span></span> |   <span data-ttu-id="36fd2-125">AdvancedQuery.Read.All</span><span class="sxs-lookup"><span data-stu-id="36fd2-125">AdvancedQuery.Read.All</span></span> |    <span data-ttu-id="36fd2-126">'Run advanced queries'</span><span class="sxs-lookup"><span data-stu-id="36fd2-126">'Run advanced queries'</span></span>
<span data-ttu-id="36fd2-127">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="36fd2-127">Delegated (work or school account)</span></span> | <span data-ttu-id="36fd2-128">AdvancedQuery.Read</span><span class="sxs-lookup"><span data-stu-id="36fd2-128">AdvancedQuery.Read</span></span> | <span data-ttu-id="36fd2-129">'Run advanced queries'</span><span class="sxs-lookup"><span data-stu-id="36fd2-129">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="36fd2-130">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="36fd2-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="36fd2-131">Пользователю должна быть роль AD "Просмотр данных"</span><span class="sxs-lookup"><span data-stu-id="36fd2-131">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="36fd2-132">Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="36fd2-132">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="36fd2-133">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="36fd2-133">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a><span data-ttu-id="36fd2-134">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="36fd2-134">Request headers</span></span>

<span data-ttu-id="36fd2-135">Заголовок</span><span class="sxs-lookup"><span data-stu-id="36fd2-135">Header</span></span> | <span data-ttu-id="36fd2-136">Значение</span><span class="sxs-lookup"><span data-stu-id="36fd2-136">Value</span></span> 
:---|:---
<span data-ttu-id="36fd2-137">Авторизация</span><span class="sxs-lookup"><span data-stu-id="36fd2-137">Authorization</span></span> | <span data-ttu-id="36fd2-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="36fd2-138">Bearer {token}.</span></span> <span data-ttu-id="36fd2-139">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="36fd2-139">**Required**.</span></span>
<span data-ttu-id="36fd2-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="36fd2-140">Content-Type</span></span>    | <span data-ttu-id="36fd2-141">application/json</span><span class="sxs-lookup"><span data-stu-id="36fd2-141">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="36fd2-142">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="36fd2-142">Request body</span></span>
<span data-ttu-id="36fd2-143">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="36fd2-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="36fd2-144">Параметр</span><span class="sxs-lookup"><span data-stu-id="36fd2-144">Parameter</span></span> | <span data-ttu-id="36fd2-145">Тип</span><span class="sxs-lookup"><span data-stu-id="36fd2-145">Type</span></span>    | <span data-ttu-id="36fd2-146">Описание</span><span class="sxs-lookup"><span data-stu-id="36fd2-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="36fd2-147">Запрос</span><span class="sxs-lookup"><span data-stu-id="36fd2-147">Query</span></span> | <span data-ttu-id="36fd2-148">Текст</span><span class="sxs-lookup"><span data-stu-id="36fd2-148">Text</span></span> |  <span data-ttu-id="36fd2-149">Запрос для выполнения.</span><span class="sxs-lookup"><span data-stu-id="36fd2-149">The query to run.</span></span> <span data-ttu-id="36fd2-150">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="36fd2-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="36fd2-151">Отклик</span><span class="sxs-lookup"><span data-stu-id="36fd2-151">Response</span></span>
<span data-ttu-id="36fd2-152">В случае успешного выполнения этот метод возвращает 200 ОК и _объект QueryResponse_ в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="36fd2-152">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="36fd2-153">Пример</span><span class="sxs-lookup"><span data-stu-id="36fd2-153">Example</span></span>

<span data-ttu-id="36fd2-154">Запрос</span><span class="sxs-lookup"><span data-stu-id="36fd2-154">Request</span></span>

<span data-ttu-id="36fd2-155">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="36fd2-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

<span data-ttu-id="36fd2-156">Отклик</span><span class="sxs-lookup"><span data-stu-id="36fd2-156">Response</span></span>

<span data-ttu-id="36fd2-157">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="36fd2-157">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="36fd2-158">Показанный здесь объект ответа может быть усечен для краткости.</span><span class="sxs-lookup"><span data-stu-id="36fd2-158">The response object shown here may be truncated for brevity.</span></span> <span data-ttu-id="36fd2-159">При фактическом вызове будут возвращены все свойства.</span><span class="sxs-lookup"><span data-stu-id="36fd2-159">All of the properties will be returned from an actual call.</span></span>

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="36fd2-160">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="36fd2-160">Related topic</span></span>
- [<span data-ttu-id="36fd2-161">Microsoft Defender для внедрения API конечных точек</span><span class="sxs-lookup"><span data-stu-id="36fd2-161">Microsoft Defender for Endpoint APIs introduction</span></span>](apis-intro.md)
- [<span data-ttu-id="36fd2-162">Расширенный поиск с портала</span><span class="sxs-lookup"><span data-stu-id="36fd2-162">Advanced Hunting from Portal</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="36fd2-163">Расширенный метод охоты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="36fd2-163">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)