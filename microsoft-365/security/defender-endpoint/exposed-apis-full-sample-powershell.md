---
title: Расширенный справочник по охоте с API PowerShell
ms.reviewer: ''
description: Используйте эти примеры кода, запросив несколько API Microsoft Defender для конечных точек.
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
ms.date: 09/24/2018
ms.technology: mde
ms.openlocfilehash: ef6d05bb27018bb72f731da2e8b7837c9d9f0127
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842066"
---
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a>Microsoft Defender для API конечных точек с помощью PowerShell

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Полный сценарий с использованием нескольких API из Microsoft Defender для конечной точки.

В этом разделе мы делимся примерами PowerShell с 
- Извлечение маркера 
- Использование маркера для получения последних оповещений в Microsoft Defender для конечной точки
- Для каждого оповещения, если оповещение имеет средний или высокий приоритет и все еще находится в процессе выполнения, проверьте, сколько раз устройство подключено к подозрительному URL-адресу.

**Обязательное** условие. Сначала [необходимо создать приложение.](apis-intro.md)

## <a name="preparation-instructions"></a>Инструкции по подготовке

- Откройте окно PowerShell.
- Если политика не позволяет запускать команды PowerShell, можно выполнить приведенную ниже команду:
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

Дополнительные сведения см. в [документации PowerShell](/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>Get token

Запустите ниже:

- $tenantId: ID клиента, от имени которого требуется выполнить запрос (то есть запрос будет работать на данных этого клиента)
- $appId: ID приложения AAD (приложение должно иметь разрешение "Выполнить расширенные запросы" в Defender для конечной точки)
- $appSecret: Секрет приложения Azure AD

- $suspiciousUrl: URL-адрес


```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here
$suspiciousUrl = 'www.suspiciousUrl.com' # Paste your own URL here

$resourceAppIdUri = 'https://securitycenter.onmicrosoft.com/windowsatpservice'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$aadToken = $authResponse.access_token


#Get latest alert
$alertUrl = "https://api.securitycenter.microsoft.com/api/alerts?`$top=10"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$alertResponse = Invoke-WebRequest -Method Get -Uri $alertUrl -Headers $headers -ErrorAction Stop
$alerts =  ($alertResponse | ConvertFrom-Json).value

$machinesToInvestigate = New-Object System.Collections.ArrayList

Foreach($alert in $alerts)
{
    #echo $alert.id $alert.machineId    $alert.severity $alert.status

    $isSevereAlert = $alert.severity -in 'Medium', 'High'
    $isOpenAlert = $alert.status -in 'InProgress', 'New'
    if($isOpenAlert -and $isSevereAlert)
    {
        if (-not $machinesToInvestigate.Contains($alert.machineId))
        {
            $machinesToInvestigate.Add($alert.machineId) > $null
        }
    }
}

$commaSeparatedMachines = '"{0}"' -f ($machinesToInvestigate -join '","')

$query = "NetworkCommunicationEvents
| where MachineId in ($commaSeparatedMachines)
| where RemoteUrl  == `"$suspiciousUrl`"
| summarize ConnectionsCount = count() by MachineId"

$queryUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"

$queryBody = ConvertTo-Json -InputObject @{ 'Query' = $query }
$queryResponse = Invoke-WebRequest -Method Post -Uri $queryUrl -Headers $headers -Body $queryBody -ErrorAction Stop
$response =  ($queryResponse | ConvertFrom-Json).Results
$response
```


## <a name="see-also"></a>См. также
- [Microsoft Defender для API конечных точек](apis-intro.md)
- [Программный интерфейс расширенной охоты](run-advanced-query-api.md)
- [Расширенная охота с помощью Python](run-advanced-query-sample-python.md)
