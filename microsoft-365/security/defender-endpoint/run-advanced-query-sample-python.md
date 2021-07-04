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
ms.openlocfilehash: 7ee431c88430916fcba60266a3a3a5180d830c0d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289263"
---
# <a name="advanced-hunting-using-python"></a>Расширенная охота с помощью Python

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Запустите расширенные запросы с помощью Python, см. [расширенный API охоты.](run-advanced-query-api.md)

В этом разделе мы делимся примерами Python, чтобы получить маркер и использовать его для выполнения запроса.

> **Обязательное** условие. Сначала [необходимо создать приложение.](apis-intro.md)

## <a name="get-token"></a>Get token

- Выполните следующие команды:

```python
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

где

- tenantId. ID клиента, от имени которого требуется выполнить запрос (то есть запрос будет работать на данных этого клиента)
- appId: ID приложения Azure AD (приложение должно иметь разрешение "Выполнить расширенные запросы" в Microsoft Defender для конечной точки)
- appSecret: секрет приложения Azure AD

## <a name="run-query"></a>Запуск запроса

 Запустите следующий запрос:

```python
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

- схема содержит схему результатов запроса
- результаты содержат результаты запроса

### <a name="complex-queries"></a>Сложные запросы

Если вы хотите выполнить сложные запросы (или многоуровневые запросы), сохраните запрос в файле и вместо первой строки в приведенном выше примере запустите ниже команду:

```python
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a>Работа с результатами запросов

Теперь можно использовать результаты запроса.

Чтобы итерировать результаты, сделайте ниже:

```python
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result
```

Для вывода результатов запроса в формате CSV в файле file1.csv ниже:

```python
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

Для вывода результатов запроса в формате JSON в файле file1.jsдалее:

```python
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```

## <a name="related-topic"></a>Связанная тема

- [Microsoft Defender для API конечных точек](apis-intro.md)
- [API расширенной охоты](run-advanced-query-api.md)
- [Расширенная охота с помощью PowerShell](run-advanced-query-sample-powershell.md)
