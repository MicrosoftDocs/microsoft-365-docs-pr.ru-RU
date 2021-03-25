---
title: Advanced Hunting with PowerShell API Basics
ms.reviewer: ''
description: Узнайте основы запроса API Microsoft Defender для конечной точки с помощью PowerShell.
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
ms.openlocfilehash: 20c63daaf61b85f35aaceccb540b6d50824c801d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198675"
---
# <a name="advanced-hunting-using-powershell"></a><span data-ttu-id="5c4ed-104">Расширенный метод охоты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c4ed-104">Advanced Hunting using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5c4ed-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5c4ed-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="5c4ed-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5c4ed-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5c4ed-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="5c4ed-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="5c4ed-108">Запустите расширенные запросы с помощью PowerShell, см. [расширенный API охоты.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="5c4ed-108">Run advanced queries using PowerShell, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="5c4ed-109">В этом разделе мы делимся примерами PowerShell для получения маркера и использования его для выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="5c4ed-109">In this section, we share PowerShell samples to retrieve a token and use it to run a query.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5c4ed-110">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="5c4ed-110">Before you begin</span></span>
<span data-ttu-id="5c4ed-111">Сначала необходимо [создать приложение.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5c4ed-111">You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="5c4ed-112">Инструкции по подготовке</span><span class="sxs-lookup"><span data-stu-id="5c4ed-112">Preparation instructions</span></span>

- <span data-ttu-id="5c4ed-113">Откройте окно PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c4ed-113">Open a PowerShell window.</span></span>
- <span data-ttu-id="5c4ed-114">Если политика не позволяет запускать команды PowerShell, можно выполнить приведенную ниже команду:</span><span class="sxs-lookup"><span data-stu-id="5c4ed-114">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

><span data-ttu-id="5c4ed-115">Дополнительные сведения см. в [документации PowerShell](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="5c4ed-115">For more information, see [PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="5c4ed-116">Get token</span><span class="sxs-lookup"><span data-stu-id="5c4ed-116">Get token</span></span>

- <span data-ttu-id="5c4ed-117">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5c4ed-117">Run the following:</span></span>

```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$body = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$response = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $body -ErrorAction Stop
$aadToken = $response.access_token
```

<span data-ttu-id="5c4ed-118">где</span><span class="sxs-lookup"><span data-stu-id="5c4ed-118">where</span></span>
- <span data-ttu-id="5c4ed-119">$tenantId: ID клиента, от имени которого требуется выполнить запрос (то есть запрос будет работать на данных этого клиента)</span><span class="sxs-lookup"><span data-stu-id="5c4ed-119">$tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="5c4ed-120">$appId: ID приложения Azure AD (приложение должно иметь разрешение на выполнение расширенных запросов в Defender для конечной точки)</span><span class="sxs-lookup"><span data-stu-id="5c4ed-120">$appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="5c4ed-121">$appSecret: Секрет приложения Azure AD</span><span class="sxs-lookup"><span data-stu-id="5c4ed-121">$appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="5c4ed-122">Запуск запроса</span><span class="sxs-lookup"><span data-stu-id="5c4ed-122">Run query</span></span>

<span data-ttu-id="5c4ed-123">Запустите следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="5c4ed-123">Run the following query:</span></span>

```
$query = 'RegistryEvents | limit 10' # Paste your own query here

$url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$body = ConvertTo-Json -InputObject @{ 'Query' = $query }
$webResponse = Invoke-WebRequest -Method Post -Uri $url -Headers $headers -Body $body -ErrorAction Stop
$response =  $webResponse | ConvertFrom-Json
$results = $response.Results
$schema = $response.Schema
```

- <span data-ttu-id="5c4ed-124">$results содержат результаты запроса</span><span class="sxs-lookup"><span data-stu-id="5c4ed-124">$results contain the results of your query</span></span>
- <span data-ttu-id="5c4ed-125">$schema содержит схему результатов запроса</span><span class="sxs-lookup"><span data-stu-id="5c4ed-125">$schema contains the schema of the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="5c4ed-126">Сложные запросы</span><span class="sxs-lookup"><span data-stu-id="5c4ed-126">Complex queries</span></span>

<span data-ttu-id="5c4ed-127">Если вы хотите запускать сложные запросы (или многолинейные запросы), сохраните запрос в файле и вместо первой строки в приведенном выше примере запустите приведенную ниже команду:</span><span class="sxs-lookup"><span data-stu-id="5c4ed-127">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a><span data-ttu-id="5c4ed-128">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="5c4ed-128">Work with query results</span></span>

<span data-ttu-id="5c4ed-129">Теперь можно использовать результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="5c4ed-129">You can now use the query results.</span></span>

<span data-ttu-id="5c4ed-130">Для вывода результатов запроса в формате CSV в файле file1.csv ниже:</span><span class="sxs-lookup"><span data-stu-id="5c4ed-130">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

<span data-ttu-id="5c4ed-131">Для вывода результатов запроса в формате JSON в файле file1.jsдалее:</span><span class="sxs-lookup"><span data-stu-id="5c4ed-131">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a><span data-ttu-id="5c4ed-132">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="5c4ed-132">Related topic</span></span>
- [<span data-ttu-id="5c4ed-133">Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="5c4ed-133">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="5c4ed-134">Программный интерфейс расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="5c4ed-134">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="5c4ed-135">Расширенный метод охоты с помощью Python</span><span class="sxs-lookup"><span data-stu-id="5c4ed-135">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)