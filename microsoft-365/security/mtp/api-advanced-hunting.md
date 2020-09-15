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
ms.openlocfilehash: 92d5d2840963ae00ae0f03e3359f287371f770ee
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650510"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="696a6-104">Расширенные API поисковых интерфейсов</span><span class="sxs-lookup"><span data-stu-id="696a6-104">Advanced hunting APIs</span></span>

<span data-ttu-id="696a6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="696a6-105">**Applies to:**</span></span>
- <span data-ttu-id="696a6-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="696a6-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="696a6-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="696a6-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="696a6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="696a6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="696a6-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="696a6-109">Limitations</span></span>
1. <span data-ttu-id="696a6-110">Запрос данных можно выполнить только за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="696a6-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="696a6-111">В результаты будет включено не более 100 000 строк.</span><span class="sxs-lookup"><span data-stu-id="696a6-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="696a6-112">Количество выполнений ограничено для каждого клиента: до 15 вызовов в минуту, 15 минут времени выполнения — каждый час и 4 часа выполнения в день.</span><span class="sxs-lookup"><span data-stu-id="696a6-112">The number of executions is limited per tenant: up to 15 calls per minute, 15 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="696a6-113">Максимальное время выполнения одного запроса составляет 10 минут.</span><span class="sxs-lookup"><span data-stu-id="696a6-113">The maximal execution time of a single request is 10 minutes.</span></span>

## <a name="permissions"></a><span data-ttu-id="696a6-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="696a6-114">Permissions</span></span>
<span data-ttu-id="696a6-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="696a6-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="696a6-116">Дополнительные сведения, в том числе выбор разрешений, приведены [в статье Access API защиты от угроз Майкрософт](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="696a6-116">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="696a6-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="696a6-117">Permission type</span></span> |   <span data-ttu-id="696a6-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="696a6-118">Permission</span></span>  |   <span data-ttu-id="696a6-119">Отображаемое имя разрешения</span><span class="sxs-lookup"><span data-stu-id="696a6-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="696a6-120">Для приложений</span><span class="sxs-lookup"><span data-stu-id="696a6-120">Application</span></span> |   <span data-ttu-id="696a6-121">Адванцедхунтинг. Read. ALL</span><span class="sxs-lookup"><span data-stu-id="696a6-121">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="696a6-122">"Выполнение расширенных запросов"</span><span class="sxs-lookup"><span data-stu-id="696a6-122">'Run advanced queries'</span></span>
<span data-ttu-id="696a6-123">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="696a6-123">Delegated (work or school account)</span></span> | <span data-ttu-id="696a6-124">Адванцедхунтинг. Read</span><span class="sxs-lookup"><span data-stu-id="696a6-124">AdvancedHunting.Read</span></span> | <span data-ttu-id="696a6-125">"Выполнение расширенных запросов"</span><span class="sxs-lookup"><span data-stu-id="696a6-125">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="696a6-126">При получении маркера с использованием учетных данных пользователя:</span><span class="sxs-lookup"><span data-stu-id="696a6-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="696a6-127">Пользователь должен иметь роль AD "View Data"</span><span class="sxs-lookup"><span data-stu-id="696a6-127">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="696a6-128">Пользователь должен иметь доступ к устройству на основе параметров группы устройств.</span><span class="sxs-lookup"><span data-stu-id="696a6-128">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="696a6-129">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="696a6-129">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="696a6-130">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="696a6-130">Request headers</span></span>

<span data-ttu-id="696a6-131">Заголовок</span><span class="sxs-lookup"><span data-stu-id="696a6-131">Header</span></span> | <span data-ttu-id="696a6-132">Значение</span><span class="sxs-lookup"><span data-stu-id="696a6-132">Value</span></span> 
:---|:---
<span data-ttu-id="696a6-133">Авторизация</span><span class="sxs-lookup"><span data-stu-id="696a6-133">Authorization</span></span> | <span data-ttu-id="696a6-134">Bearer {Token}.</span><span class="sxs-lookup"><span data-stu-id="696a6-134">Bearer {token}.</span></span> <span data-ttu-id="696a6-135">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="696a6-135">**Required**.</span></span>
<span data-ttu-id="696a6-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="696a6-136">Content-Type</span></span>    | <span data-ttu-id="696a6-137">application/json</span><span class="sxs-lookup"><span data-stu-id="696a6-137">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="696a6-138">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="696a6-138">Request body</span></span>
<span data-ttu-id="696a6-139">В теле запроса добавьте объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="696a6-139">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="696a6-140">Параметр</span><span class="sxs-lookup"><span data-stu-id="696a6-140">Parameter</span></span> | <span data-ttu-id="696a6-141">Тип</span><span class="sxs-lookup"><span data-stu-id="696a6-141">Type</span></span>    | <span data-ttu-id="696a6-142">Описание</span><span class="sxs-lookup"><span data-stu-id="696a6-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="696a6-143">Запрос</span><span class="sxs-lookup"><span data-stu-id="696a6-143">Query</span></span> | <span data-ttu-id="696a6-144">Текст</span><span class="sxs-lookup"><span data-stu-id="696a6-144">Text</span></span> |  <span data-ttu-id="696a6-145">Выполняемый запрос.</span><span class="sxs-lookup"><span data-stu-id="696a6-145">The query to run.</span></span> <span data-ttu-id="696a6-146">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="696a6-146">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="696a6-147">Отклик</span><span class="sxs-lookup"><span data-stu-id="696a6-147">Response</span></span>
<span data-ttu-id="696a6-148">В случае успешного выполнения этот метод возвращает 200 ОК и объект _куериреспонсе_ в тексте отклика.</span><span class="sxs-lookup"><span data-stu-id="696a6-148">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="696a6-149">Объект Response разделен на 3 части (свойств):</span><span class="sxs-lookup"><span data-stu-id="696a6-149">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="696a6-150">```Stats``` — Статистика производительности запросов.</span><span class="sxs-lookup"><span data-stu-id="696a6-150">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="696a6-151">```Schema``` — Схема ответа, список пар "имя — тип" для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="696a6-151">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="696a6-152">```Results``` — Список событий расширенного поискового элемента.</span><span class="sxs-lookup"><span data-stu-id="696a6-152">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="696a6-153">Пример</span><span class="sxs-lookup"><span data-stu-id="696a6-153">Example</span></span>

<span data-ttu-id="696a6-154">Запрос</span><span class="sxs-lookup"><span data-stu-id="696a6-154">Request</span></span>

<span data-ttu-id="696a6-155">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="696a6-155">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="696a6-156">Отклик</span><span class="sxs-lookup"><span data-stu-id="696a6-156">Response</span></span>

<span data-ttu-id="696a6-157">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="696a6-157">Here is an example of the response.</span></span>


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

## <a name="related-topic"></a><span data-ttu-id="696a6-158">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="696a6-158">Related topic</span></span>
- [<span data-ttu-id="696a6-159">Доступ к API защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="696a6-159">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
