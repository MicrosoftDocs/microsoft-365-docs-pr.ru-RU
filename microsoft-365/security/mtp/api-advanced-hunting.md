---
title: Расширенные API поисковых интерфейсов
description: Узнайте, как выполнять расширенные поисковые запросы с помощью API Microsoft Threat protection
keywords: Расширенный поиск, API, API, MTP
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
ms.openlocfilehash: 9e92a0328d2e7fb9cfe7461241dd866081926876
ms.sourcegitcommit: 62a8c226422eac9c085cc886b4836b037f95ef6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "47825378"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="854f9-104">Расширенные API поисковых интерфейсов</span><span class="sxs-lookup"><span data-stu-id="854f9-104">Advanced hunting APIs</span></span>

<span data-ttu-id="854f9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="854f9-105">**Applies to:**</span></span>
- <span data-ttu-id="854f9-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="854f9-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="854f9-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="854f9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="854f9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="854f9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="854f9-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="854f9-109">Limitations</span></span>
1. <span data-ttu-id="854f9-110">Запрос данных можно выполнить только за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="854f9-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="854f9-111">В результаты будет включено не более 100 000 строк.</span><span class="sxs-lookup"><span data-stu-id="854f9-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="854f9-112">Количество выполнений ограничено для каждого клиента: до 10 вызовов в минуту, 10 минут времени выполнения в час и 4 часа выполнения в день.</span><span class="sxs-lookup"><span data-stu-id="854f9-112">The number of executions is limited per tenant: up to 10 calls per minute, 10 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="854f9-113">Максимальное время выполнения одного запроса составляет 10 минут.</span><span class="sxs-lookup"><span data-stu-id="854f9-113">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="854f9-114">429 ответ будет представлять предельную квоту либо по количеству запросов, либо по ЦП.</span><span class="sxs-lookup"><span data-stu-id="854f9-114">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="854f9-115">Текст ответа 429 также будет указывать время до продления квоты.</span><span class="sxs-lookup"><span data-stu-id="854f9-115">The 429 response body will also indicate the time until the quota is renewed.</span></span> 


## <a name="permissions"></a><span data-ttu-id="854f9-116">Разрешения</span><span class="sxs-lookup"><span data-stu-id="854f9-116">Permissions</span></span>
<span data-ttu-id="854f9-117">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="854f9-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="854f9-118">Дополнительные сведения, в том числе выбор разрешений, приведены [в статье Access API защиты от угроз Майкрософт](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="854f9-118">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="854f9-119">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="854f9-119">Permission type</span></span> |   <span data-ttu-id="854f9-120">Разрешение</span><span class="sxs-lookup"><span data-stu-id="854f9-120">Permission</span></span>  |   <span data-ttu-id="854f9-121">Отображаемое имя разрешения</span><span class="sxs-lookup"><span data-stu-id="854f9-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="854f9-122">Для приложений</span><span class="sxs-lookup"><span data-stu-id="854f9-122">Application</span></span> |   <span data-ttu-id="854f9-123">Адванцедхунтинг. Read. ALL</span><span class="sxs-lookup"><span data-stu-id="854f9-123">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="854f9-124">"Выполнение расширенных запросов"</span><span class="sxs-lookup"><span data-stu-id="854f9-124">'Run advanced queries'</span></span>
<span data-ttu-id="854f9-125">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="854f9-125">Delegated (work or school account)</span></span> | <span data-ttu-id="854f9-126">Адванцедхунтинг. Read</span><span class="sxs-lookup"><span data-stu-id="854f9-126">AdvancedHunting.Read</span></span> | <span data-ttu-id="854f9-127">"Выполнение расширенных запросов"</span><span class="sxs-lookup"><span data-stu-id="854f9-127">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="854f9-128">При получении маркера с использованием учетных данных пользователя:</span><span class="sxs-lookup"><span data-stu-id="854f9-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="854f9-129">Пользователь должен иметь роль AD "View Data"</span><span class="sxs-lookup"><span data-stu-id="854f9-129">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="854f9-130">Пользователь должен иметь доступ к устройству на основе параметров группы устройств.</span><span class="sxs-lookup"><span data-stu-id="854f9-130">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="854f9-131">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="854f9-131">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="854f9-132">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="854f9-132">Request headers</span></span>

<span data-ttu-id="854f9-133">Заголовок</span><span class="sxs-lookup"><span data-stu-id="854f9-133">Header</span></span> | <span data-ttu-id="854f9-134">Значение</span><span class="sxs-lookup"><span data-stu-id="854f9-134">Value</span></span> 
:---|:---
<span data-ttu-id="854f9-135">Авторизация</span><span class="sxs-lookup"><span data-stu-id="854f9-135">Authorization</span></span> | <span data-ttu-id="854f9-136">Bearer {Token}.</span><span class="sxs-lookup"><span data-stu-id="854f9-136">Bearer {token}.</span></span> <span data-ttu-id="854f9-137">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="854f9-137">**Required**.</span></span>
<span data-ttu-id="854f9-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="854f9-138">Content-Type</span></span>    | <span data-ttu-id="854f9-139">application/json</span><span class="sxs-lookup"><span data-stu-id="854f9-139">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="854f9-140">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="854f9-140">Request body</span></span>
<span data-ttu-id="854f9-141">В теле запроса добавьте объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="854f9-141">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="854f9-142">Параметр</span><span class="sxs-lookup"><span data-stu-id="854f9-142">Parameter</span></span> | <span data-ttu-id="854f9-143">Тип</span><span class="sxs-lookup"><span data-stu-id="854f9-143">Type</span></span>    | <span data-ttu-id="854f9-144">Описание</span><span class="sxs-lookup"><span data-stu-id="854f9-144">Description</span></span>
:---|:---|:---
<span data-ttu-id="854f9-145">Запрос</span><span class="sxs-lookup"><span data-stu-id="854f9-145">Query</span></span> | <span data-ttu-id="854f9-146">Текст</span><span class="sxs-lookup"><span data-stu-id="854f9-146">Text</span></span> |  <span data-ttu-id="854f9-147">Выполняемый запрос.</span><span class="sxs-lookup"><span data-stu-id="854f9-147">The query to run.</span></span> <span data-ttu-id="854f9-148">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="854f9-148">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="854f9-149">Отклик</span><span class="sxs-lookup"><span data-stu-id="854f9-149">Response</span></span>
<span data-ttu-id="854f9-150">В случае успешного выполнения этот метод возвращает 200 ОК и объект _куериреспонсе_ в тексте отклика.</span><span class="sxs-lookup"><span data-stu-id="854f9-150">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="854f9-151">Объект Response разделен на 3 части (свойств):</span><span class="sxs-lookup"><span data-stu-id="854f9-151">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="854f9-152">```Stats``` — Статистика производительности запросов.</span><span class="sxs-lookup"><span data-stu-id="854f9-152">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="854f9-153">```Schema``` — Схема ответа, список пар "имя — тип" для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="854f9-153">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="854f9-154">```Results``` — Список событий расширенного поискового элемента.</span><span class="sxs-lookup"><span data-stu-id="854f9-154">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="854f9-155">Пример</span><span class="sxs-lookup"><span data-stu-id="854f9-155">Example</span></span>

<span data-ttu-id="854f9-156">Запрос</span><span class="sxs-lookup"><span data-stu-id="854f9-156">Request</span></span>

<span data-ttu-id="854f9-157">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="854f9-157">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="854f9-158">Отклик</span><span class="sxs-lookup"><span data-stu-id="854f9-158">Response</span></span>

<span data-ttu-id="854f9-159">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="854f9-159">Here is an example of the response.</span></span>


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

## <a name="related-topic"></a><span data-ttu-id="854f9-160">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="854f9-160">Related topic</span></span>
- [<span data-ttu-id="854f9-161">Доступ к API защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="854f9-161">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
