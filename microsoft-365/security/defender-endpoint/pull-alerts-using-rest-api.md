---
title: Pull Microsoft Defender для обнаружения конечных точек с помощью API REST
description: Узнайте, как вызвать конечную точку API API Microsoft Defender для конечной точки, чтобы вытащить обнаружения в формате JSON с помощью API SIEM REST.
keywords: обнаружения, обнаружения тяги, api отдыха, запроса, ответа
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: c8baf74d5f838c583b98fddd7d7d706c6e116a40
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071910"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a>Pull Microsoft Defender for Endpoint detections using SIEM REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- [Microsoft Defender for Endpoint Alert](alerts.md) состоит из одного или нескольких обнаружений.
>- [Microsoft Defender for Endpoint Detection](api-portal-mapping.md) состоит из подозрительного события, произошедшего на устройстве, и связанных с ним сведений оповещения.
>-API оповещений Microsoft Defender для конечной точки является последним API для потребления оповещений и содержит подробный список связанных данных для каждого оповещения. Дополнительные сведения см. в [дополнительных сведениях о](alerts.md) методах и свойствах alert и [list alerts.](get-alerts.md)

Microsoft Defender для конечной точки поддерживает протокол OAuth 2.0, чтобы вытащить обнаружения из API.

Как правило, протокол OAuth 2.0 поддерживает четыре типа потоков:
- Поток грантов авторизации
- Неявный поток
- Поток клиентских учетных данных
- Поток владельцев ресурсов

Дополнительные сведения о спецификациях OAuth см. на сайте [OAuth.](http://www.oauth.net)

Microsoft Defender для конечной  точки  поддерживает поток грантов авторизации и поток учетных данных клиента для получения доступа к обнаружениям тяги, а Azure Active Directory (AAD) является сервером авторизации.

Поток _грантов авторизации_ использует учетные данные пользователей для получения кода авторизации, который затем используется для получения маркера доступа.

Поток _учетных данных клиента_ использует учетные данные клиента для проверки подлинности в отношении URL-адреса конечной точки Microsoft Defender для конечной точки. Этот поток подходит для сценариев, когда клиент OAuth создает запросы в API, не требуя учетных данных пользователей.

Используйте следующий метод в API Microsoft Defender для конечной точки, чтобы вытащить обнаружения в формате JSON.

>[!NOTE]
>Центр безопасности Microsoft Defender объединяет аналогичные обнаружения оповещений в единое оповещение. Этот API извлекает обнаружение оповещений в сыром виде на основе заданных параметров запроса, что позволяет применять собственную группировку и фильтрацию. 

## <a name="before-you-begin"></a>Перед началом работы
- Прежде чем вызывать конечную точку Microsoft Defender для конечной точки для обнаружения, необходимо включить приложение интеграции SIEM в Azure Active Directory (AAD). Дополнительные сведения см. в [веб-сайте Включить интеграцию SIEM в Microsoft Defender для конечной точки.](enable-siem-integration.md)

- Запишите указанные ниже значения при регистрации приложения Azure. Эти значения понадобятся для настройки потока OAuth в вашей службе или управляющей программе.
  - Идентификатор клиента (уникальный для приложения)
  - Ключ, или секрет, клиента (уникальный для приложения)
  - Конечная точка маркера OAuth 2.0 приложения
    - Чтобы найти это значение, нажмите **Просмотр конечных точек** в нижней части портала управления Azure на странице приложения. Конечная точка будет представлена в формате `https://login.microsoftonline.com/{tenantId}/oauth2/token`.

## <a name="get-an-access-token"></a>Получение токена доступа
Перед созданием вызовов в конечную точку необходимо получить маркер доступа.

Маркер доступа используется для доступа к защищенного ресурса, который является обнаружением в Microsoft Defender для endpoint.

Чтобы получить маркер доступа, необходимо сделать запрос POST в конечной точке выдачи маркера. Вот пример запроса:

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
Ответ будет содержать маркер доступа и сведения об истечении срока действия.

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
Теперь вы можете использовать значение в *поле access_token* в запросе в API Defender для конечной точки.

## <a name="request"></a>Запрос
С помощью маркера доступа ваше приложение может делать запросы на проверку подлинности в API Microsoft Defender for Endpoint. Приложение должно добавлять токен доступа в заголовок Authorization каждого запроса.

### <a name="request-syntax"></a>Запрос синтаксиса
Метод | Запрос URI
:---|:---|
GET| Используйте URI, применимый к вашему региону. <br><br> **Для ЕС**: `https://wdatp-alertexporter-eu.windows.com/api/alerts` </br> **Для США**: `https://wdatp-alertexporter-us.windows.com/api/alerts` <br> **Для Великобритании**: `https://wdatp-alertexporter-uk.windows.com/api/alerts` 

### <a name="request-header"></a>Заготвка запроса
Верхний колонтитул | Тип | Описание|
:--|:--|:--
Authorization | string | Обязательное. Маркер доступа Azure AD в маркере **Bearer** &lt; *формы.* &gt; |

### <a name="request-parameters"></a>Параметры запроса

Используйте необязательные параметры запроса для указания и управления объемом данных, возвращаемого в ответ. Если вызвать этот метод без параметров, ответ содержит все оповещения в организации за последние 2 часа.

Имя | Значение| Описание
:---|:---|:---
sinceTimeUtc | DateTime | Определяет меньшее время, связанное оповещений извлекаются из, на основе поля: <br> `LastProcessedTimeUtc` <br> Диапазон времени будет: от времени sinceTimeUtc до текущего времени. <br><br> **ПРИМЕЧАНИЕ.** Если не указано, все оповещения, созданные за последние два часа, извлекаются.
untilTimeUtc | DateTime | Определяет, как извлекаются оповещений, связанных с верхним временем. <br> Диапазон времени будет: `sinceTimeUtc` время от `untilTimeUtc` времени. <br><br> **ПРИМЕЧАНИЕ.** Если не указано, значение по умолчанию будет текущим.
ago | строка | Время от времени вытягивает оповещений в следующем `(current_time - ago)` `current_time` диапазоне времени. <br><br> Значение должно быть установлено в соответствии **с форматом длительности ISO 8601** <br> Пример: `ago=PT10M` будет тянуть оповещения, полученные в течение последних 10 минут.
limit | int | Определяет количество извлеченных оповещений. Последние оповещений будут извлечены на основе определенного числа.<br><br> **ПРИМЕЧАНИЕ.** Если не указано, все оповещения, доступные в диапазоне времени, будут извлечены.
машинные группы | строка | Указывает группы устройств, чтобы вывести оповещения из. <br><br> **ПРИМЕЧАНИЕ.** Если не указано, оповещения из всех групп устройств будут извлечены. <br><br> Пример. <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/Alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
DeviceCreatedMachineTags | строка | Тег одного устройства из реестра.
CloudCreatedMachineTags | строка | Теги устройств, созданные в Центре безопасности Защитника Майкрософт.

### <a name="request-example"></a>Пример запроса
В следующем примере показано, как получить все обнаружения в организации.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

В следующем примере демонстрируется запрос на последние 20 обнаружения с 2016-09-12 00:00:00.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a>Отклик
Возвращаемая величина — это массив объектов оповещения в формате JSON.

Вот пример возвращаемой стоимости:

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a>Примеры кода
### <a name="get-access-token"></a>Получить маркер доступа
В следующих примерах кода показано, как получить маркер доступа для вызова API СИЕМ Microsoft Defender для конечной точки.

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a>Использование маркера для подключения к конечной точке обнаружения
В следующих примерах кода показано, как использовать маркер доступа для вызова API SIEM Defender для конечной точки для получения оповещений.

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a>Коды ошибок
API rest API Для защитника Конечной точки возвращает следующие коды ошибок, вызванные недействительным запросом.

Код ошибки HTTP | Описание
:---|:---
401 | Недействительный запрос или недействительный маркер.
403 | Несанкционированное исключение — любой из доменов не управляется администратором клиента или состоянием клиента удаляется.
500 | Ошибка в службе.

## <a name="related-topics"></a>Статьи по теме
- [Включение интеграции SIEM в Microsoft Defender для конечной точки](enable-siem-integration.md)
- [Настройте ArcSight, чтобы вытащить Microsoft Defender для обнаружения конечных точек](configure-arcsight.md)
- [Притягивать обнаружения к средствам SIEM](configure-siem.md)
- [Microsoft Defender для полей обнаружения конечных точек](api-portal-mapping.md)
- [Устранение неполадок в интеграции инструментов SIEM](troubleshoot-siem.md)
