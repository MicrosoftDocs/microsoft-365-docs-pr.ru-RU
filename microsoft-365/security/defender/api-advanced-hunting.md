---
title: Microsoft 365 Защитник расширенный API охоты
description: Узнайте, как запускать расширенные запросы на охоту с Microsoft 365 API для Microsoft 365 Defender.
keywords: Advanced Hunting, API, api, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3ff62265783be846a95964164e372100fe1ef662
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769590"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="84ca3-104">Microsoft 365 Defender Advanced hunting API</span><span class="sxs-lookup"><span data-stu-id="84ca3-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="84ca3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="84ca3-105">**Applies to:**</span></span>

- <span data-ttu-id="84ca3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84ca3-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84ca3-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="84ca3-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="84ca3-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="84ca3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="84ca3-109">[Расширенный поиск](advanced-hunting-overview.md) — это средство [](advanced-hunting-query-language.md) для охоты на угрозы, которое использует специально построенные запросы для изучения данных событий за последние 30 дней в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="84ca3-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="84ca3-110">Вы можете использовать расширенные запросы на охоту для проверки необычной активности, обнаружения возможных угроз и даже реагирования на атаки.</span><span class="sxs-lookup"><span data-stu-id="84ca3-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="84ca3-111">Расширенный API охоты позволяет программным образом запрашивать данные событий.</span><span class="sxs-lookup"><span data-stu-id="84ca3-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="84ca3-112">Квоты и распределение ресурсов</span><span class="sxs-lookup"><span data-stu-id="84ca3-112">Quotas and resource allocation</span></span>

<span data-ttu-id="84ca3-113">Следующие условия относятся к всем запросам.</span><span class="sxs-lookup"><span data-stu-id="84ca3-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="84ca3-114">Запросы исследуют и возвращают данные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="84ca3-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="84ca3-115">Результаты могут возвращать до 100 000 строк.</span><span class="sxs-lookup"><span data-stu-id="84ca3-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="84ca3-116">Вы можете сделать до 15 вызовов в минуту на каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="84ca3-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="84ca3-117">Запросы блокируют, если клиент достиг 100% до следующего 15-минутного цикла.</span><span class="sxs-lookup"><span data-stu-id="84ca3-117">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span>
5. <span data-ttu-id="84ca3-118">Если один запрос выполняется более 10 минут, он будет время и возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="84ca3-118">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
6. <span data-ttu-id="84ca3-119">Код ответа HTTP указывает, что вы достигли квоты либо по количеству отправленных запросов, либо по `429` выделенной продолжительной работе.</span><span class="sxs-lookup"><span data-stu-id="84ca3-119">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="84ca3-120">Ознакомьтесь с текстом ответа, чтобы понять достигнутое ограничение.</span><span class="sxs-lookup"><span data-stu-id="84ca3-120">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="84ca3-121">Все квоты, перечисленные выше (например, 15 вызовов за мин), являются для каждого клиента размером.</span><span class="sxs-lookup"><span data-stu-id="84ca3-121">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="84ca3-122">Эти квоты минимальны.</span><span class="sxs-lookup"><span data-stu-id="84ca3-122">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="84ca3-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="84ca3-123">Permissions</span></span>

<span data-ttu-id="84ca3-124">Одно из следующих разрешений необходимо для вызова продвинутого API охоты.</span><span class="sxs-lookup"><span data-stu-id="84ca3-124">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="84ca3-125">Дополнительные возможности, в том числе выбор разрешений, см. в Microsoft 365 [API защиты защитника](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="84ca3-125">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="84ca3-126">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="84ca3-126">Permission type</span></span> | <span data-ttu-id="84ca3-127">Разрешение</span><span class="sxs-lookup"><span data-stu-id="84ca3-127">Permission</span></span> | <span data-ttu-id="84ca3-128">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="84ca3-128">Permission display name</span></span>
-|-|-
<span data-ttu-id="84ca3-129">Приложение</span><span class="sxs-lookup"><span data-stu-id="84ca3-129">Application</span></span> | <span data-ttu-id="84ca3-130">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="84ca3-130">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="84ca3-131">Запуск расширенных запросов</span><span class="sxs-lookup"><span data-stu-id="84ca3-131">Run advanced queries</span></span>
<span data-ttu-id="84ca3-132">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="84ca3-132">Delegated (work or school account)</span></span> | <span data-ttu-id="84ca3-133">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="84ca3-133">AdvancedHunting.Read</span></span> | <span data-ttu-id="84ca3-134">Запуск расширенных запросов</span><span class="sxs-lookup"><span data-stu-id="84ca3-134">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="84ca3-135">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="84ca3-135">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="84ca3-136">Пользователю должна быть роль AD "View Data"</span><span class="sxs-lookup"><span data-stu-id="84ca3-136">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="84ca3-137">Пользователь должен иметь доступ к устройству в зависимости от параметров группы устройств.</span><span class="sxs-lookup"><span data-stu-id="84ca3-137">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="84ca3-138">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="84ca3-138">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="84ca3-139">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="84ca3-139">Request headers</span></span>

<span data-ttu-id="84ca3-140">Заголовок</span><span class="sxs-lookup"><span data-stu-id="84ca3-140">Header</span></span> | <span data-ttu-id="84ca3-141">Значение</span><span class="sxs-lookup"><span data-stu-id="84ca3-141">Value</span></span>
-|-
<span data-ttu-id="84ca3-142">Authorization</span><span class="sxs-lookup"><span data-stu-id="84ca3-142">Authorization</span></span> | <span data-ttu-id="84ca3-143">Bearer {token} **Примечание: требуется**</span><span class="sxs-lookup"><span data-stu-id="84ca3-143">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="84ca3-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="84ca3-144">Content-Type</span></span> | <span data-ttu-id="84ca3-145">application/json</span><span class="sxs-lookup"><span data-stu-id="84ca3-145">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="84ca3-146">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="84ca3-146">Request body</span></span>

<span data-ttu-id="84ca3-147">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="84ca3-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="84ca3-148">Параметр</span><span class="sxs-lookup"><span data-stu-id="84ca3-148">Parameter</span></span> | <span data-ttu-id="84ca3-149">Тип</span><span class="sxs-lookup"><span data-stu-id="84ca3-149">Type</span></span> | <span data-ttu-id="84ca3-150">Описание</span><span class="sxs-lookup"><span data-stu-id="84ca3-150">Description</span></span>
-|-|-
<span data-ttu-id="84ca3-151">Запрос</span><span class="sxs-lookup"><span data-stu-id="84ca3-151">Query</span></span> | <span data-ttu-id="84ca3-152">Текст</span><span class="sxs-lookup"><span data-stu-id="84ca3-152">Text</span></span> | <span data-ttu-id="84ca3-153">Запрос для выполнения.</span><span class="sxs-lookup"><span data-stu-id="84ca3-153">The query to run.</span></span> <span data-ttu-id="84ca3-154">**Примечание: требуется**</span><span class="sxs-lookup"><span data-stu-id="84ca3-154">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="84ca3-155">Отклик</span><span class="sxs-lookup"><span data-stu-id="84ca3-155">Response</span></span>

<span data-ttu-id="84ca3-156">В случае успешного выполнения этот метод `200 OK` возвращается и _объект QueryResponse_ в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="84ca3-156">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="84ca3-157">Объект ответа содержит три свойства верхнего уровня:</span><span class="sxs-lookup"><span data-stu-id="84ca3-157">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="84ca3-158">Stats — словарь статистики производительности запросов.</span><span class="sxs-lookup"><span data-stu-id="84ca3-158">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="84ca3-159">Схема — схема ответа, список Name-Type для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="84ca3-159">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="84ca3-160">Результаты — список расширенных событий охоты.</span><span class="sxs-lookup"><span data-stu-id="84ca3-160">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="84ca3-161">Пример</span><span class="sxs-lookup"><span data-stu-id="84ca3-161">Example</span></span>

<span data-ttu-id="84ca3-162">В следующем примере пользователь отправляет запрос ниже и получает объект ответа API, содержащий `Stats` , `Schema` и `Results` .</span><span class="sxs-lookup"><span data-stu-id="84ca3-162">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="84ca3-163">Запрос</span><span class="sxs-lookup"><span data-stu-id="84ca3-163">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="84ca3-164">Объект response</span><span class="sxs-lookup"><span data-stu-id="84ca3-164">Response object</span></span>

```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
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
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="84ca3-165">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="84ca3-165">Related articles</span></span>

- [<span data-ttu-id="84ca3-166">Доступ к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84ca3-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="84ca3-167">Узнайте о ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="84ca3-167">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="84ca3-168">Понимание кодов ошибок</span><span class="sxs-lookup"><span data-stu-id="84ca3-168">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="84ca3-169">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="84ca3-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
