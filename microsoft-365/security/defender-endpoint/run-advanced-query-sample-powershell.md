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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0d44f59f69c590ecd8d61207de8784af3e32197d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844890"
---
# <a name="advanced-hunting-using-powershell"></a>Расширенная охота с помощью PowerShell

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Запустите расширенные запросы с помощью PowerShell, см. [расширенный API охоты.](run-advanced-query-api.md)

В этом разделе мы делимся примерами PowerShell для получения маркера и использования его для выполнения запроса.

## <a name="before-you-begin"></a>Прежде чем начать
Сначала необходимо [создать приложение.](apis-intro.md)

## <a name="preparation-instructions"></a>Инструкции по подготовке

- Откройте окно PowerShell.
- Если политика не позволяет запускать команды PowerShell, можно выполнить приведенную ниже команду:
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

>Дополнительные сведения см. в [документации PowerShell](/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>Get token

- Выполните следующую команду:

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

где
- $tenantId: ID клиента, от имени которого требуется выполнить запрос (то есть запрос будет работать на данных этого клиента)
- $appId: ID приложения Azure AD (приложение должно иметь разрешение на выполнение расширенных запросов в Defender для конечной точки)
- $appSecret: Секрет приложения Azure AD

## <a name="run-query"></a>Запуск запроса

Запустите следующий запрос:

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

- $results содержат результаты запроса
- $schema содержит схему результатов запроса

### <a name="complex-queries"></a>Сложные запросы

Если вы хотите запускать сложные запросы (или многолинейные запросы), сохраните запрос в файле и вместо первой строки в приведенном выше примере запустите приведенную ниже команду:

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a>Работа с результатами запросов

Теперь можно использовать результаты запроса.

Для вывода результатов запроса в формате CSV в файле file1.csv ниже:

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

Для вывода результатов запроса в формате JSON в файле file1.jsдалее:

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a>Связанная тема
- [Microsoft Defender для API конечных точек](apis-intro.md)
- [Программный интерфейс расширенной охоты](run-advanced-query-api.md)
- [Расширенная охота с помощью Python](run-advanced-query-sample-python.md)
