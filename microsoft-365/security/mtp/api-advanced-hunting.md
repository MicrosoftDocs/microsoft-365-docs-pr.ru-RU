---
title: API расширенных поисков в Защитнике Microsoft 365
description: Узнайте, как запускать запросы на расширенный поиск с помощью API advanced hunting в Microsoft 365 Defender
keywords: Расширенный поиск, API, API, MTP, Защитник M365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e7cd9192ec25e01ed06b77cb2b39357cb9df79bd
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719384"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="5f349-104">Microsoft 365 Defender Advanced hunting API</span><span class="sxs-lookup"><span data-stu-id="5f349-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5f349-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5f349-105">**Applies to:**</span></span>

- <span data-ttu-id="5f349-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="5f349-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f349-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="5f349-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5f349-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="5f349-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="5f349-109">[Расширенный поиск](advanced-hunting-overview.md) — это средство [](advanced-hunting-query-language.md) охоты на угрозы, которое использует специально построенные запросы для изучения данных событий за последние 30 дней в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="5f349-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="5f349-110">Вы можете использовать расширенные поисковые запросы для проверки необычных действий, обнаружения возможных угроз и даже реагирования на атаки.</span><span class="sxs-lookup"><span data-stu-id="5f349-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="5f349-111">API расширенных запросов позволяет программным образом запрашивать данные событий.</span><span class="sxs-lookup"><span data-stu-id="5f349-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="5f349-112">Квоты и выделение ресурсов</span><span class="sxs-lookup"><span data-stu-id="5f349-112">Quotas and resource allocation</span></span>

<span data-ttu-id="5f349-113">Следующие условия относятся к всем запросам.</span><span class="sxs-lookup"><span data-stu-id="5f349-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="5f349-114">Запросы изучают и возвращают данные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="5f349-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="5f349-115">Результаты могут возвращать до 100 000 строк.</span><span class="sxs-lookup"><span data-stu-id="5f349-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="5f349-116">Вы можете делать до 10 вызовов в минуту на клиента.</span><span class="sxs-lookup"><span data-stu-id="5f349-116">You can make up to 10 calls per minute per tenant.</span></span>
4. <span data-ttu-id="5f349-117">У вас есть 10 минут времени работы в час на клиента.</span><span class="sxs-lookup"><span data-stu-id="5f349-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="5f349-118">Общее время работы клиента составляет четыре часа.</span><span class="sxs-lookup"><span data-stu-id="5f349-118">You have four total hours of running time day per tenant.</span></span>
6. <span data-ttu-id="5f349-119">Если один запрос выполняется более 10 минут, время его времени и возвратит ошибку.</span><span class="sxs-lookup"><span data-stu-id="5f349-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="5f349-120">Код http-ответа указывает, что вы достигли квоты по количеству отправленных запросов или по выделению `429` времени работы.</span><span class="sxs-lookup"><span data-stu-id="5f349-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="5f349-121">Тело ответа будет включать время, пока квота не будет сброшена.</span><span class="sxs-lookup"><span data-stu-id="5f349-121">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="5f349-122">Разрешения</span><span class="sxs-lookup"><span data-stu-id="5f349-122">Permissions</span></span>

<span data-ttu-id="5f349-123">Для вызова API advanced hunting требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="5f349-123">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="5f349-124">Дополнительные возможности, включая выбор разрешений, см. в API Access для Защиты От защитника [Microsoft 365](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="5f349-124">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="5f349-125">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="5f349-125">Permission type</span></span> | <span data-ttu-id="5f349-126">Разрешение</span><span class="sxs-lookup"><span data-stu-id="5f349-126">Permission</span></span> | <span data-ttu-id="5f349-127">Отображаемая имя разрешения</span><span class="sxs-lookup"><span data-stu-id="5f349-127">Permission display name</span></span>
-|-|-
<span data-ttu-id="5f349-128">Приложение</span><span class="sxs-lookup"><span data-stu-id="5f349-128">Application</span></span> | <span data-ttu-id="5f349-129">AdvancedАting.Read.All</span><span class="sxs-lookup"><span data-stu-id="5f349-129">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="5f349-130">Выполнение расширенных запросов</span><span class="sxs-lookup"><span data-stu-id="5f349-130">Run advanced queries</span></span>
<span data-ttu-id="5f349-131">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="5f349-131">Delegated (work or school account)</span></span> | <span data-ttu-id="5f349-132">AdvancedАting.Read</span><span class="sxs-lookup"><span data-stu-id="5f349-132">AdvancedHunting.Read</span></span> | <span data-ttu-id="5f349-133">Выполнение расширенных запросов</span><span class="sxs-lookup"><span data-stu-id="5f349-133">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="5f349-134">При получении маркера с использованием учетных данных пользователя:</span><span class="sxs-lookup"><span data-stu-id="5f349-134">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="5f349-135">Пользователю требуется роль AD "Просмотр данных"</span><span class="sxs-lookup"><span data-stu-id="5f349-135">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="5f349-136">Пользователь должен иметь доступ к устройству на основе параметров группы устройств.</span><span class="sxs-lookup"><span data-stu-id="5f349-136">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="5f349-137">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="5f349-137">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="5f349-138">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="5f349-138">Request headers</span></span>

<span data-ttu-id="5f349-139">Заголовок</span><span class="sxs-lookup"><span data-stu-id="5f349-139">Header</span></span> | <span data-ttu-id="5f349-140">Значение</span><span class="sxs-lookup"><span data-stu-id="5f349-140">Value</span></span>
-|-
<span data-ttu-id="5f349-141">Авторизация</span><span class="sxs-lookup"><span data-stu-id="5f349-141">Authorization</span></span> | <span data-ttu-id="5f349-142">Bearer {token} **Note: required**</span><span class="sxs-lookup"><span data-stu-id="5f349-142">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="5f349-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="5f349-143">Content-Type</span></span> | <span data-ttu-id="5f349-144">application/json</span><span class="sxs-lookup"><span data-stu-id="5f349-144">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="5f349-145">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="5f349-145">Request body</span></span>

<span data-ttu-id="5f349-146">В теле запроса укажу объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="5f349-146">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="5f349-147">Параметр</span><span class="sxs-lookup"><span data-stu-id="5f349-147">Parameter</span></span> | <span data-ttu-id="5f349-148">Тип</span><span class="sxs-lookup"><span data-stu-id="5f349-148">Type</span></span> | <span data-ttu-id="5f349-149">Описание</span><span class="sxs-lookup"><span data-stu-id="5f349-149">Description</span></span>
-|-|-
<span data-ttu-id="5f349-150">Запрос</span><span class="sxs-lookup"><span data-stu-id="5f349-150">Query</span></span> | <span data-ttu-id="5f349-151">Текст</span><span class="sxs-lookup"><span data-stu-id="5f349-151">Text</span></span> | <span data-ttu-id="5f349-152">Запрос, который необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="5f349-152">The query to run.</span></span> <span data-ttu-id="5f349-153">**Примечание. обязательно**</span><span class="sxs-lookup"><span data-stu-id="5f349-153">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="5f349-154">Отклик</span><span class="sxs-lookup"><span data-stu-id="5f349-154">Response</span></span>

<span data-ttu-id="5f349-155">В случае успешного выполнения этот метод возвращает объект `200 OK` _QueryResponse_ в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="5f349-155">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="5f349-156">Объект ответа содержит три свойства верхнего уровня:</span><span class="sxs-lookup"><span data-stu-id="5f349-156">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="5f349-157">Статистика — словарь статистики производительности запросов.</span><span class="sxs-lookup"><span data-stu-id="5f349-157">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="5f349-158">Схема — схема ответа, список Name-Type для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="5f349-158">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="5f349-159">Результаты — список событий расширенных охоты.</span><span class="sxs-lookup"><span data-stu-id="5f349-159">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="5f349-160">Пример</span><span class="sxs-lookup"><span data-stu-id="5f349-160">Example</span></span>

<span data-ttu-id="5f349-161">В следующем примере пользователь отправляет запрос ниже и получает объект ответа API, содержащий `Stats` , `Schema` и `Results` .</span><span class="sxs-lookup"><span data-stu-id="5f349-161">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="5f349-162">Запрос</span><span class="sxs-lookup"><span data-stu-id="5f349-162">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="5f349-163">Объект Response</span><span class="sxs-lookup"><span data-stu-id="5f349-163">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="5f349-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5f349-164">Related articles</span></span>

- [<span data-ttu-id="5f349-165">Доступ к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f349-165">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="5f349-166">Узнайте об ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="5f349-166">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="5f349-167">Коды ошибок</span><span class="sxs-lookup"><span data-stu-id="5f349-167">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="5f349-168">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="5f349-168">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
