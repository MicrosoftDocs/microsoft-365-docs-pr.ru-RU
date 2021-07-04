---
title: API оповещений списка
description: Узнайте, как использовать API оповещений List для получения коллекции оповещений в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.openlocfilehash: dcc8a9214e0a6d0a0ede3b08aa6a019f2f0c4d2c
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289851"
---
# <a name="list-alerts-api"></a><span data-ttu-id="e3d06-104">API оповещений списка</span><span class="sxs-lookup"><span data-stu-id="e3d06-104">List alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e3d06-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e3d06-105">**Applies to:**</span></span>
- [<span data-ttu-id="e3d06-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e3d06-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e3d06-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3d06-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e3d06-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e3d06-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e3d06-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="e3d06-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e3d06-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="e3d06-110">API description</span></span>
<span data-ttu-id="e3d06-111">Извлекает коллекцию оповещений.</span><span class="sxs-lookup"><span data-stu-id="e3d06-111">Retrieves a collection of Alerts.</span></span>
<br><span data-ttu-id="e3d06-112">Поддерживает [запросы OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="e3d06-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="e3d06-113">Операторы, поддерживаемые OData:</span><span class="sxs-lookup"><span data-stu-id="e3d06-113">OData supported operators:</span></span>
<br><span data-ttu-id="e3d06-114">```$filter``` on: ```alertCreationTime``` ```lastUpdateTime``` , , , , , ```incidentId``` ```InvestigationId``` и ```status``` ```severity``` ```category``` свойства.</span><span class="sxs-lookup"><span data-stu-id="e3d06-114">```$filter``` on: ```alertCreationTime```, ```lastUpdateTime```, ```incidentId```,```InvestigationId```, ```status```, ```severity``` and ```category``` properties.</span></span>
<br><span data-ttu-id="e3d06-115">```$top``` максимальное значение 10 000</span><span class="sxs-lookup"><span data-stu-id="e3d06-115">```$top``` with max value of 10,000</span></span>
<br>```$skip```
<br><span data-ttu-id="e3d06-116">```$expand``` из ```evidence```</span><span class="sxs-lookup"><span data-stu-id="e3d06-116">```$expand``` of ```evidence```</span></span>
<br><span data-ttu-id="e3d06-117">Примеры запросов [OData в Microsoft Defender для конечной точки](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="e3d06-117">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="e3d06-118">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e3d06-118">Limitations</span></span>
1. <span data-ttu-id="e3d06-119">Вы можете получать последние обновления оповещений в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="e3d06-119">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="e3d06-120">Максимальный размер страницы — 10 000.</span><span class="sxs-lookup"><span data-stu-id="e3d06-120">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="e3d06-121">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="e3d06-121">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="e3d06-122">Разрешения</span><span class="sxs-lookup"><span data-stu-id="e3d06-122">Permissions</span></span>
<span data-ttu-id="e3d06-123">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="e3d06-123">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e3d06-124">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e3d06-124">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e3d06-125">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="e3d06-125">Permission type</span></span> | <span data-ttu-id="e3d06-126">Разрешение</span><span class="sxs-lookup"><span data-stu-id="e3d06-126">Permission</span></span> | <span data-ttu-id="e3d06-127">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="e3d06-127">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e3d06-128">Application</span><span class="sxs-lookup"><span data-stu-id="e3d06-128">Application</span></span> | <span data-ttu-id="e3d06-129">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="e3d06-129">Alert.Read.All</span></span> | <span data-ttu-id="e3d06-130">'Read all alerts'</span><span class="sxs-lookup"><span data-stu-id="e3d06-130">'Read all alerts'</span></span>
<span data-ttu-id="e3d06-131">Application</span><span class="sxs-lookup"><span data-stu-id="e3d06-131">Application</span></span> | <span data-ttu-id="e3d06-132">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e3d06-132">Alert.ReadWrite.All</span></span> | <span data-ttu-id="e3d06-133">'Read and write all alerts'</span><span class="sxs-lookup"><span data-stu-id="e3d06-133">'Read and write all alerts'</span></span>
<span data-ttu-id="e3d06-134">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="e3d06-134">Delegated (work or school account)</span></span> | <span data-ttu-id="e3d06-135">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="e3d06-135">Alert.Read</span></span> | <span data-ttu-id="e3d06-136">'Read alerts'</span><span class="sxs-lookup"><span data-stu-id="e3d06-136">'Read alerts'</span></span>
<span data-ttu-id="e3d06-137">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="e3d06-137">Delegated (work or school account)</span></span> | <span data-ttu-id="e3d06-138">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e3d06-138">Alert.ReadWrite</span></span> | <span data-ttu-id="e3d06-139">'Read and write alerts'</span><span class="sxs-lookup"><span data-stu-id="e3d06-139">'Read and write alerts'</span></span>

> [!NOTE]
> <span data-ttu-id="e3d06-140">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="e3d06-140">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="e3d06-141">Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="e3d06-141">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="e3d06-142">В ответ будут включены только оповещения, связанные с устройствами, к которые пользователь может получить доступ на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="e3d06-142">The response will include only alerts that are associated with devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e3d06-143">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="e3d06-143">HTTP request</span></span>

```http
GET /api/alerts
```

## <a name="request-headers"></a><span data-ttu-id="e3d06-144">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="e3d06-144">Request headers</span></span>

<span data-ttu-id="e3d06-145">Имя</span><span class="sxs-lookup"><span data-stu-id="e3d06-145">Name</span></span> | <span data-ttu-id="e3d06-146">Тип</span><span class="sxs-lookup"><span data-stu-id="e3d06-146">Type</span></span> | <span data-ttu-id="e3d06-147">Описание</span><span class="sxs-lookup"><span data-stu-id="e3d06-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="e3d06-148">Authorization</span><span class="sxs-lookup"><span data-stu-id="e3d06-148">Authorization</span></span> | <span data-ttu-id="e3d06-149">Строка</span><span class="sxs-lookup"><span data-stu-id="e3d06-149">String</span></span> | <span data-ttu-id="e3d06-150">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e3d06-150">Bearer {token}.</span></span> <span data-ttu-id="e3d06-151">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="e3d06-151">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e3d06-152">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="e3d06-152">Request body</span></span>

<span data-ttu-id="e3d06-153">переменная Empty</span><span class="sxs-lookup"><span data-stu-id="e3d06-153">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e3d06-154">Отклик</span><span class="sxs-lookup"><span data-stu-id="e3d06-154">Response</span></span>

<span data-ttu-id="e3d06-155">В случае успеха этот метод возвращает 200 [](alerts.md) ОК и список объектов оповещения в теле отклика.</span><span class="sxs-lookup"><span data-stu-id="e3d06-155">If successful, this method returns 200 OK, and a list of [alert](alerts.md) objects in the response body.</span></span>

## <a name="example-1---default"></a><span data-ttu-id="e3d06-156">Пример 1 . По умолчанию</span><span class="sxs-lookup"><span data-stu-id="e3d06-156">Example 1 - Default</span></span>

### <a name="request"></a><span data-ttu-id="e3d06-157">Запрос</span><span class="sxs-lookup"><span data-stu-id="e3d06-157">Request</span></span>

<span data-ttu-id="e3d06-158">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="e3d06-158">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts
```

### <a name="response"></a><span data-ttu-id="e3d06-159">Отклик</span><span class="sxs-lookup"><span data-stu-id="e3d06-159">Response</span></span>

<span data-ttu-id="e3d06-160">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="e3d06-160">Here is an example of the response.</span></span>

> [!NOTE]
> <span data-ttu-id="e3d06-161">Список ответов, показанный здесь, может быть усечен для краткости.</span><span class="sxs-lookup"><span data-stu-id="e3d06-161">The response list shown here may be truncated for brevity.</span></span> <span data-ttu-id="e3d06-162">Все оповещения будут возвращены с фактического вызова.</span><span class="sxs-lookup"><span data-stu-id="e3d06-162">All alerts will be returned from an actual call.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Alerts",
    "value": [
        {
            "id": "da637308392288907382_-880718168",
            "incidentId": 7587,
            "investigationId": 723156,
            "assignedTo": "secop123@contoso.com",
            "severity": "Low",
            "status": "New",
            "classification": "TruePositive",
            "determination": null,
            "investigationState": "Queued",
            "detectionSource": "WindowsDefenderAv",
            "category": "SuspiciousActivity",
            "threatFamilyName": "Meterpreter",
            "title": "Suspicious 'Meterpreter' behavior was detected",
            "description": "Malware and unwanted software are undesirable applications that perform annoying, disruptive, or harmful actions on affected machines. Some of these undesirable applications can replicate and spread from one machine to another. Others are able to receive commands from remote attackers and perform activities associated with cyber attacks.\n\nA malware is considered active if it is found running on the machine or it already has persistence mechanisms in place. Active malware detections are assigned higher severity ratings.\n\nBecause this malware was active, take precautionary measures and check for residual signs of infection.",
            "alertCreationTime": "2020-07-20T10:53:48.7657932Z",
            "firstEventTime": "2020-07-20T10:52:17.6654369Z",
            "lastEventTime": "2020-07-20T10:52:18.1362905Z",
            "lastUpdateTime": "2020-07-20T10:53:50.19Z",
            "resolvedTime": null,
            "machineId": "12ee6dd8c833c8a052ea231ec1b19adaf497b625",
            "computerDnsName": "temp123.middleeast.corp.microsoft.com",
            "rbacGroupName": "MiddleEast",
            "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
            "threatName": null,
            "mitreTechniques": [
                "T1064",
                "T1085",
                "T1220"
            ],
            "relatedUser": {
                "userName": "temp123",
                "domainName": "MIDDLEEAST"
            },
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2020-07-21T01:00:37.8404534Z"
                }
            ],
            "evidence": []
        }
        ...
    ]
}
```

## <a name="example-2---get-10-latest-alerts-with-related-evidence"></a><span data-ttu-id="e3d06-163">Пример 2 . Получить 10 последних оповещений со связанными доказательствами</span><span class="sxs-lookup"><span data-stu-id="e3d06-163">Example 2 - Get 10 latest Alerts with related Evidence</span></span>

### <a name="request"></a><span data-ttu-id="e3d06-164">Запрос</span><span class="sxs-lookup"><span data-stu-id="e3d06-164">Request</span></span>

<span data-ttu-id="e3d06-165">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="e3d06-165">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts?$top=10&$expand=evidence
```

### <a name="response"></a><span data-ttu-id="e3d06-166">Отклик</span><span class="sxs-lookup"><span data-stu-id="e3d06-166">Response</span></span>

<span data-ttu-id="e3d06-167">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="e3d06-167">Here is an example of the response.</span></span>

> [!NOTE]
> <span data-ttu-id="e3d06-168">Список ответов, показанный здесь, может быть усечен для краткости.</span><span class="sxs-lookup"><span data-stu-id="e3d06-168">The response list shown here may be truncated for brevity.</span></span> <span data-ttu-id="e3d06-169">Все оповещения будут возвращены с фактического вызова.</span><span class="sxs-lookup"><span data-stu-id="e3d06-169">All alerts will be returned from an actual call.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Alerts",
    "value": [
        {
            "id": "da637472900382838869_1364969609",
            "incidentId": 1126093,
            "investigationId": null,
            "assignedTo": null,
            "severity": "Low",
            "status": "New",
            "classification": null,
            "determination": null,
            "investigationState": "Queued",
            "detectionSource": "WindowsDefenderAtp",
            "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
            "category": "Execution",
            "threatFamilyName": null,
            "title": "Low-reputation arbitrary code executed by signed executable",
            "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
            "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
            "firstEventTime": "2021-01-26T20:31:32.9562661Z",
            "lastEventTime": "2021-01-26T20:31:33.0577322Z",
            "lastUpdateTime": "2021-01-26T20:33:59.2Z",
            "resolvedTime": null,
            "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
            "computerDnsName": "temp123.middleeast.corp.microsoft.com",
            "rbacGroupName": "A",
            "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
            "threatName": null,
            "mitreTechniques": [
                "T1064",
                "T1085",
                "T1220"
            ],
            "relatedUser": {
                "userName": "temp123",
                "domainName": "MIDDLEEAST"
            },
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "evidence": [
                {
                    "entityType": "User",
                    "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
                    "sha1": null,
                    "sha256": null,
                    "fileName": null,
                    "filePath": null,
                    "processId": null,
                    "processCommandLine": null,
                    "processCreationTime": null,
                    "parentProcessId": null,
                    "parentProcessCreationTime": null,
                    "parentProcessFileName": null,
                    "parentProcessFilePath": null,
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": "eranb",
                    "domainName": "MIDDLEEAST",
                    "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
                    "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
                    "userPrincipalName": "temp123@microsoft.com",
                    "detectionStatus": null
                },
                {
                    "entityType": "Process",
                    "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
                    "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
                    "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
                    "fileName": "rundll32.exe",
                    "filePath": "C:\\Windows\\SysWOW64",
                    "processId": 3276,
                    "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
                    "processCreationTime": "2021-01-26T20:31:32.9581596Z",
                    "parentProcessId": 8420,
                    "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
                    "parentProcessFileName": "rundll32.exe",
                    "parentProcessFilePath": "C:\\Windows\\System32",
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": null,
                    "domainName": null,
                    "userSid": null,
                    "aadUserId": null,
                    "userPrincipalName": null,
                    "detectionStatus": "Detected"
                },
                {
                    "entityType": "File",
                    "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
                    "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
                    "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
                    "fileName": "suspicious.dll",
                    "filePath": "c:\\temp",
                    "processId": null,
                    "processCommandLine": null,
                    "processCreationTime": null,
                    "parentProcessId": null,
                    "parentProcessCreationTime": null,
                    "parentProcessFileName": null,
                    "parentProcessFilePath": null,
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": null,
                    "domainName": null,
                    "userSid": null,
                    "aadUserId": null,
                    "userPrincipalName": null,
                    "detectionStatus": "Detected"
                }
            ]
        },
        ...
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="e3d06-170">См. также</span><span class="sxs-lookup"><span data-stu-id="e3d06-170">See also</span></span>

[<span data-ttu-id="e3d06-171">Запросы OData в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e3d06-171">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
