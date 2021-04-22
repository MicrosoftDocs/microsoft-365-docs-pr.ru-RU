---
title: Microsoft 365 Defender расширенный API охоты
description: Узнайте, как запускать расширенные запросы на охоту с помощью API microsoft 365 Defender для охоты
keywords: Advanced Hunting, APIs, api, M365 Defender, Microsoft 365 Defender
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
ms.openlocfilehash: c988a609a329c8f7f8988314e56aae942beebac5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932897"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="282f8-104">Microsoft 365 Defender Advanced hunting API</span><span class="sxs-lookup"><span data-stu-id="282f8-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="282f8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="282f8-105">**Applies to:**</span></span>

- <span data-ttu-id="282f8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="282f8-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="282f8-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="282f8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="282f8-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="282f8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="282f8-109">[Расширенный поиск](advanced-hunting-overview.md) — это средство [](advanced-hunting-query-language.md) для охоты на угрозы, которое использует специально построенные запросы для изучения данных событий за последние 30 дней в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="282f8-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="282f8-110">Вы можете использовать расширенные запросы на охоту для проверки необычной активности, обнаружения возможных угроз и даже реагирования на атаки.</span><span class="sxs-lookup"><span data-stu-id="282f8-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="282f8-111">Расширенный API охоты позволяет программным образом запрашивать данные событий.</span><span class="sxs-lookup"><span data-stu-id="282f8-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="282f8-112">Квоты и распределение ресурсов</span><span class="sxs-lookup"><span data-stu-id="282f8-112">Quotas and resource allocation</span></span>

<span data-ttu-id="282f8-113">Следующие условия относятся к всем запросам.</span><span class="sxs-lookup"><span data-stu-id="282f8-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="282f8-114">Запросы исследуют и возвращают данные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="282f8-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="282f8-115">Результаты могут возвращать до 100 000 строк.</span><span class="sxs-lookup"><span data-stu-id="282f8-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="282f8-116">Вы можете сделать до 15 вызовов в минуту на каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="282f8-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="282f8-117">У вас есть 10 минут времени работы в час на каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="282f8-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="282f8-118">Общее время работы в день на каждого клиента составляет четыре часа.</span><span class="sxs-lookup"><span data-stu-id="282f8-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="282f8-119">Если один запрос выполняется более 10 минут, он будет время и возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="282f8-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="282f8-120">Код ответа HTTP указывает, что вы достигли квоты либо по количеству отправленных запросов, либо по `429` выделенной продолжительной работе.</span><span class="sxs-lookup"><span data-stu-id="282f8-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="282f8-121">Ознакомьтесь с текстом ответа, чтобы понять достигнутое ограничение.</span><span class="sxs-lookup"><span data-stu-id="282f8-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="282f8-122">Все квоты, перечисленные выше (например, 15 вызовов за мин), являются для каждого клиента размером.</span><span class="sxs-lookup"><span data-stu-id="282f8-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="282f8-123">Эти квоты минимальны.</span><span class="sxs-lookup"><span data-stu-id="282f8-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="282f8-124">Разрешения</span><span class="sxs-lookup"><span data-stu-id="282f8-124">Permissions</span></span>

<span data-ttu-id="282f8-125">Одно из следующих разрешений необходимо для вызова продвинутого API охоты.</span><span class="sxs-lookup"><span data-stu-id="282f8-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="282f8-126">Дополнительные возможности, в том числе выбор разрешений, см. в aPI [Access the Microsoft 365 Defender Protection](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="282f8-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="282f8-127">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="282f8-127">Permission type</span></span> | <span data-ttu-id="282f8-128">Разрешение</span><span class="sxs-lookup"><span data-stu-id="282f8-128">Permission</span></span> | <span data-ttu-id="282f8-129">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="282f8-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="282f8-130">Приложение</span><span class="sxs-lookup"><span data-stu-id="282f8-130">Application</span></span> | <span data-ttu-id="282f8-131">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="282f8-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="282f8-132">Запуск расширенных запросов</span><span class="sxs-lookup"><span data-stu-id="282f8-132">Run advanced queries</span></span>
<span data-ttu-id="282f8-133">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="282f8-133">Delegated (work or school account)</span></span> | <span data-ttu-id="282f8-134">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="282f8-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="282f8-135">Запуск расширенных запросов</span><span class="sxs-lookup"><span data-stu-id="282f8-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="282f8-136">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="282f8-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="282f8-137">Пользователю должна быть роль AD "View Data"</span><span class="sxs-lookup"><span data-stu-id="282f8-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="282f8-138">Пользователь должен иметь доступ к устройству в зависимости от параметров группы устройств.</span><span class="sxs-lookup"><span data-stu-id="282f8-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="282f8-139">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="282f8-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="282f8-140">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="282f8-140">Request headers</span></span>

<span data-ttu-id="282f8-141">Заголовок</span><span class="sxs-lookup"><span data-stu-id="282f8-141">Header</span></span> | <span data-ttu-id="282f8-142">Значение</span><span class="sxs-lookup"><span data-stu-id="282f8-142">Value</span></span>
-|-
<span data-ttu-id="282f8-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="282f8-143">Authorization</span></span> | <span data-ttu-id="282f8-144">Bearer {token} **Примечание: требуется**</span><span class="sxs-lookup"><span data-stu-id="282f8-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="282f8-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="282f8-145">Content-Type</span></span> | <span data-ttu-id="282f8-146">application/json</span><span class="sxs-lookup"><span data-stu-id="282f8-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="282f8-147">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="282f8-147">Request body</span></span>

<span data-ttu-id="282f8-148">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="282f8-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="282f8-149">Параметр</span><span class="sxs-lookup"><span data-stu-id="282f8-149">Parameter</span></span> | <span data-ttu-id="282f8-150">Тип</span><span class="sxs-lookup"><span data-stu-id="282f8-150">Type</span></span> | <span data-ttu-id="282f8-151">Описание</span><span class="sxs-lookup"><span data-stu-id="282f8-151">Description</span></span>
-|-|-
<span data-ttu-id="282f8-152">Запрос</span><span class="sxs-lookup"><span data-stu-id="282f8-152">Query</span></span> | <span data-ttu-id="282f8-153">Текст</span><span class="sxs-lookup"><span data-stu-id="282f8-153">Text</span></span> | <span data-ttu-id="282f8-154">Запрос для выполнения.</span><span class="sxs-lookup"><span data-stu-id="282f8-154">The query to run.</span></span> <span data-ttu-id="282f8-155">**Примечание: требуется**</span><span class="sxs-lookup"><span data-stu-id="282f8-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="282f8-156">Отклик</span><span class="sxs-lookup"><span data-stu-id="282f8-156">Response</span></span>

<span data-ttu-id="282f8-157">В случае успешного выполнения этот метод `200 OK` возвращается и _объект QueryResponse_ в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="282f8-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="282f8-158">Объект ответа содержит три свойства верхнего уровня:</span><span class="sxs-lookup"><span data-stu-id="282f8-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="282f8-159">Stats — словарь статистики производительности запросов.</span><span class="sxs-lookup"><span data-stu-id="282f8-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="282f8-160">Схема — схема ответа, список Name-Type для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="282f8-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="282f8-161">Результаты — список расширенных событий охоты.</span><span class="sxs-lookup"><span data-stu-id="282f8-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="282f8-162">Пример</span><span class="sxs-lookup"><span data-stu-id="282f8-162">Example</span></span>

<span data-ttu-id="282f8-163">В следующем примере пользователь отправляет запрос ниже и получает объект ответа API, содержащий `Stats` , `Schema` и `Results` .</span><span class="sxs-lookup"><span data-stu-id="282f8-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="282f8-164">Запрос</span><span class="sxs-lookup"><span data-stu-id="282f8-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="282f8-165">Объект response</span><span class="sxs-lookup"><span data-stu-id="282f8-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="282f8-166">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="282f8-166">Related articles</span></span>

- [<span data-ttu-id="282f8-167">Доступ к API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="282f8-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="282f8-168">Узнайте о ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="282f8-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="282f8-169">Понимание кодов ошибок</span><span class="sxs-lookup"><span data-stu-id="282f8-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="282f8-170">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="282f8-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
