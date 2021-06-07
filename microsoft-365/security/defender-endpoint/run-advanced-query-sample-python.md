---
title: Расширенный справочник по охоте с API Python
ms.reviewer: ''
description: Узнайте, как запрашивать с помощью API Microsoft Defender для конечной точки с помощью Python с примерами.
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 17ad28121935adfc958629f7999311c11a8d784e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771454"
---
# <a name="advanced-hunting-using-python"></a><span data-ttu-id="a10f7-104">Расширенная охота с помощью Python</span><span class="sxs-lookup"><span data-stu-id="a10f7-104">Advanced Hunting using Python</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a10f7-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a10f7-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="a10f7-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a10f7-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a10f7-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="a10f7-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="a10f7-108">Запустите расширенные запросы с помощью Python, см. [расширенный API охоты.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="a10f7-108">Run advanced queries using Python, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="a10f7-109">В этом разделе мы делимся примерами Python, чтобы получить маркер и использовать его для выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="a10f7-109">In this section, we share Python samples to retrieve a token and use it to run a query.</span></span>

><span data-ttu-id="a10f7-110">**Обязательное** условие. Сначала [необходимо создать приложение.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a10f7-110">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="get-token"></a><span data-ttu-id="a10f7-111">Get token</span><span class="sxs-lookup"><span data-stu-id="a10f7-111">Get token</span></span>

- <span data-ttu-id="a10f7-112">Выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="a10f7-112">Run the following commands:</span></span>

```

import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.microsoftonline.com/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]

```

<span data-ttu-id="a10f7-113">где</span><span class="sxs-lookup"><span data-stu-id="a10f7-113">where</span></span>
- <span data-ttu-id="a10f7-114">tenantId. ID клиента, от имени которого требуется выполнить запрос (то есть запрос будет работать на данных этого клиента)</span><span class="sxs-lookup"><span data-stu-id="a10f7-114">tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="a10f7-115">appId: ID приложения Azure AD (приложение должно иметь разрешение "Выполнить расширенные запросы" в Microsoft Defender для конечной точки)</span><span class="sxs-lookup"><span data-stu-id="a10f7-115">appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Microsoft Defender for Endpoint)</span></span>
- <span data-ttu-id="a10f7-116">appSecret: секрет приложения Azure AD</span><span class="sxs-lookup"><span data-stu-id="a10f7-116">appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="a10f7-117">Запуск запроса</span><span class="sxs-lookup"><span data-stu-id="a10f7-117">Run query</span></span>

 <span data-ttu-id="a10f7-118">Запустите следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="a10f7-118">Run the following query:</span></span>

```
query = 'RegistryEvents | limit 10' # Paste your own query here

url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
headers = { 
    'Content-Type' : 'application/json',
    'Accept' : 'application/json',
    'Authorization' : "Bearer " + aadToken
}

data = json.dumps({ 'Query' : query }).encode("utf-8")

req = urllib.request.Request(url, data, headers)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
schema = jsonResponse["Schema"]
results = jsonResponse["Results"]

```

- <span data-ttu-id="a10f7-119">схема содержит схему результатов запроса</span><span class="sxs-lookup"><span data-stu-id="a10f7-119">schema contains the schema of the results of your query</span></span>
- <span data-ttu-id="a10f7-120">результаты содержат результаты запроса</span><span class="sxs-lookup"><span data-stu-id="a10f7-120">results contain the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="a10f7-121">Сложные запросы</span><span class="sxs-lookup"><span data-stu-id="a10f7-121">Complex queries</span></span>

<span data-ttu-id="a10f7-122">Если вы хотите запускать сложные запросы (или многолинейные запросы), сохраните запрос в файле и вместо первой строки в приведенном выше примере запустите приведенную ниже команду:</span><span class="sxs-lookup"><span data-stu-id="a10f7-122">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a><span data-ttu-id="a10f7-123">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="a10f7-123">Work with query results</span></span>

<span data-ttu-id="a10f7-124">Теперь можно использовать результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="a10f7-124">You can now use the query results.</span></span>

<span data-ttu-id="a10f7-125">Чтобы итерировать результаты, сделайте ниже:</span><span class="sxs-lookup"><span data-stu-id="a10f7-125">To iterate over the results do the below:</span></span>

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


<span data-ttu-id="a10f7-126">Для вывода результатов запроса в формате CSV в файле file1.csv ниже:</span><span class="sxs-lookup"><span data-stu-id="a10f7-126">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

<span data-ttu-id="a10f7-127">Для вывода результатов запроса в формате JSON в файле file1.jsдалее:</span><span class="sxs-lookup"><span data-stu-id="a10f7-127">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a><span data-ttu-id="a10f7-128">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="a10f7-128">Related topic</span></span>
- [<span data-ttu-id="a10f7-129">Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="a10f7-129">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="a10f7-130">Программный интерфейс расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="a10f7-130">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="a10f7-131">Расширенная охота с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="a10f7-131">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
