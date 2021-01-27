---
title: API расширенных поисков в Защитнике Microsoft 365
description: Узнайте, как запускать запросы на расширенный поиск с помощью API advanced hunting в Microsoft 365 Defender
keywords: Расширенный поиск, API, API, MTP, Защитник M365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 99f39a10de6231a72220c5c2a90ec915b1a4e44a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988120"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="48158-104">Microsoft 365 Defender Advanced hunting API</span><span class="sxs-lookup"><span data-stu-id="48158-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="48158-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="48158-105">**Applies to:**</span></span>

- <span data-ttu-id="48158-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="48158-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48158-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="48158-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="48158-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="48158-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="48158-109">[Расширенный поиск](advanced-hunting-overview.md) — это средство [](advanced-hunting-query-language.md) охоты на угрозы, которое использует специально построенные запросы для изучения данных событий за последние 30 дней в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="48158-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="48158-110">Вы можете использовать расширенные поисковые запросы для проверки необычных действий, обнаружения возможных угроз и даже реагирования на атаки.</span><span class="sxs-lookup"><span data-stu-id="48158-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="48158-111">API расширенных запросов позволяет программным образом запрашивать данные событий.</span><span class="sxs-lookup"><span data-stu-id="48158-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="48158-112">Квоты и выделение ресурсов</span><span class="sxs-lookup"><span data-stu-id="48158-112">Quotas and resource allocation</span></span>

<span data-ttu-id="48158-113">Следующие условия относятся к всем запросам.</span><span class="sxs-lookup"><span data-stu-id="48158-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="48158-114">Запросы изучают и возвращают данные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="48158-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="48158-115">Результаты могут возвращать до 100 000 строк.</span><span class="sxs-lookup"><span data-stu-id="48158-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="48158-116">Вы можете делать до 15 вызовов в минуту на клиента.</span><span class="sxs-lookup"><span data-stu-id="48158-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="48158-117">У вас есть 10 минут времени работы в час на клиента.</span><span class="sxs-lookup"><span data-stu-id="48158-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="48158-118">Общее время работы на клиенте составляет четыре часа в день.</span><span class="sxs-lookup"><span data-stu-id="48158-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="48158-119">Если один запрос выполняется более 10 минут, время его времени и возвратит ошибку.</span><span class="sxs-lookup"><span data-stu-id="48158-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="48158-120">Код отклика HTTP указывает, что вы достигли квоты по количеству отправленных запросов или по выделению `429` времени работы.</span><span class="sxs-lookup"><span data-stu-id="48158-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="48158-121">Прочитайте текст ответа, чтобы понять достигнутое ограничение.</span><span class="sxs-lookup"><span data-stu-id="48158-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="48158-122">Все квоты, перечисленные выше (например, 15 вызовов на мин), имеют размер клиента.</span><span class="sxs-lookup"><span data-stu-id="48158-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="48158-123">Эти квоты являются минимальными.</span><span class="sxs-lookup"><span data-stu-id="48158-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="48158-124">Разрешения</span><span class="sxs-lookup"><span data-stu-id="48158-124">Permissions</span></span>

<span data-ttu-id="48158-125">Для вызова API advanced hunting требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="48158-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="48158-126">Дополнительные узнать, в том числе о том, как выбрать разрешения, см. в API Access для Защиты [Защитника Microsoft 365](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="48158-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="48158-127">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="48158-127">Permission type</span></span> | <span data-ttu-id="48158-128">Разрешение</span><span class="sxs-lookup"><span data-stu-id="48158-128">Permission</span></span> | <span data-ttu-id="48158-129">Отображаемая имя разрешения</span><span class="sxs-lookup"><span data-stu-id="48158-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="48158-130">Для приложений</span><span class="sxs-lookup"><span data-stu-id="48158-130">Application</span></span> | <span data-ttu-id="48158-131">AdvancedАting.Read.All</span><span class="sxs-lookup"><span data-stu-id="48158-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="48158-132">Выполнение расширенных запросов</span><span class="sxs-lookup"><span data-stu-id="48158-132">Run advanced queries</span></span>
<span data-ttu-id="48158-133">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="48158-133">Delegated (work or school account)</span></span> | <span data-ttu-id="48158-134">AdvancedАting.Read</span><span class="sxs-lookup"><span data-stu-id="48158-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="48158-135">Выполнение расширенных запросов</span><span class="sxs-lookup"><span data-stu-id="48158-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="48158-136">При получении маркера с использованием учетных данных пользователя:</span><span class="sxs-lookup"><span data-stu-id="48158-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="48158-137">Пользователю требуется роль AD "Просмотр данных"</span><span class="sxs-lookup"><span data-stu-id="48158-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="48158-138">Пользователь должен иметь доступ к устройству на основе параметров группы устройств.</span><span class="sxs-lookup"><span data-stu-id="48158-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="48158-139">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="48158-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="48158-140">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="48158-140">Request headers</span></span>

<span data-ttu-id="48158-141">Заголовок</span><span class="sxs-lookup"><span data-stu-id="48158-141">Header</span></span> | <span data-ttu-id="48158-142">Значение</span><span class="sxs-lookup"><span data-stu-id="48158-142">Value</span></span>
-|-
<span data-ttu-id="48158-143">Авторизация</span><span class="sxs-lookup"><span data-stu-id="48158-143">Authorization</span></span> | <span data-ttu-id="48158-144">Bearer {token} **Note: required**</span><span class="sxs-lookup"><span data-stu-id="48158-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="48158-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="48158-145">Content-Type</span></span> | <span data-ttu-id="48158-146">application/json</span><span class="sxs-lookup"><span data-stu-id="48158-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="48158-147">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="48158-147">Request body</span></span>

<span data-ttu-id="48158-148">В теле запроса укажу объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="48158-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="48158-149">Параметр</span><span class="sxs-lookup"><span data-stu-id="48158-149">Parameter</span></span> | <span data-ttu-id="48158-150">Тип</span><span class="sxs-lookup"><span data-stu-id="48158-150">Type</span></span> | <span data-ttu-id="48158-151">Описание</span><span class="sxs-lookup"><span data-stu-id="48158-151">Description</span></span>
-|-|-
<span data-ttu-id="48158-152">Запрос</span><span class="sxs-lookup"><span data-stu-id="48158-152">Query</span></span> | <span data-ttu-id="48158-153">Текст</span><span class="sxs-lookup"><span data-stu-id="48158-153">Text</span></span> | <span data-ttu-id="48158-154">Запрос, который необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="48158-154">The query to run.</span></span> <span data-ttu-id="48158-155">**Примечание. обязательно**</span><span class="sxs-lookup"><span data-stu-id="48158-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="48158-156">Отклик</span><span class="sxs-lookup"><span data-stu-id="48158-156">Response</span></span>

<span data-ttu-id="48158-157">В случае успешного выполнения этот метод возвращает объект `200 OK` _QueryResponse_ в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="48158-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="48158-158">Объект ответа содержит три свойства верхнего уровня:</span><span class="sxs-lookup"><span data-stu-id="48158-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="48158-159">Статистика — словарь статистики производительности запросов.</span><span class="sxs-lookup"><span data-stu-id="48158-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="48158-160">Схема — схема ответа, список Name-Type для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="48158-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="48158-161">Результаты — список событий расширенных охоты.</span><span class="sxs-lookup"><span data-stu-id="48158-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="48158-162">Пример</span><span class="sxs-lookup"><span data-stu-id="48158-162">Example</span></span>

<span data-ttu-id="48158-163">В следующем примере пользователь отправляет запрос ниже и получает объект ответа API, содержащий `Stats` , `Schema` и `Results` .</span><span class="sxs-lookup"><span data-stu-id="48158-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="48158-164">Запрос</span><span class="sxs-lookup"><span data-stu-id="48158-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="48158-165">Объект Response</span><span class="sxs-lookup"><span data-stu-id="48158-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="48158-166">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="48158-166">Related articles</span></span>

- [<span data-ttu-id="48158-167">Доступ к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48158-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="48158-168">Узнайте об ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="48158-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="48158-169">Коды ошибок</span><span class="sxs-lookup"><span data-stu-id="48158-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="48158-170">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="48158-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
