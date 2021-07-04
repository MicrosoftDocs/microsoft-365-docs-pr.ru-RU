---
title: Получить API оповещений
description: Узнайте о методах и свойствах типа ресурса Alert в Microsoft Defender для конечной точки.
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
ms.openlocfilehash: df1a032ffab0490c41edc7d282f0f2cc60608870
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289683"
---
# <a name="alert-resource-type"></a>Тип ресурса оповещений

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a>Методы

Метод |Возвращаемый тип |Описание
:---|:---|:---
[Получение оповещения](get-alert-info-by-id.md) | [Оповещение](alerts.md) | Получите один объект [оповещения.](alerts.md)
[Список оповещений](get-alerts.md) | [Коллекция оповещений](alerts.md) | Список [оповещений.](alerts.md)
[Обновление оповещения](update-alert.md) | [Оповещение](alerts.md) | Обновление определенного [оповещения](alerts.md).
[Пакетные оповещения об обновлении](batch-update-alerts.md) | | Обновление пакета [оповещений.](alerts.md)
[Создание оповещения](create-alert-by-reference.md)|[Оповещение](alerts.md)|Создание оповещений на основе данных событий, полученных из [Advanced Hunting.](run-advanced-query-api.md)
[Списки связанных доменов](get-alert-related-domain-info.md)|Коллекция доменов| Список URL-адресов, связанных с оповещением.
[Файлы, связанные со списком](get-alert-related-files-info.md) | [Коллекция](files.md) файлов |  Список [сущностями](files.md) файлов, связанных с [оповещением.](alerts.md)
[IPs, связанные со списком](get-alert-related-ip-info.md) | Коллекция IP | Список IPs, связанных с оповещением.
[Получить связанные машины](get-alert-related-machine-info.md) | [Компьютер](machine.md) | [Машина,](machine.md) связанная с оповещением. [](alerts.md)
[Получить связанных пользователей](get-alert-related-user-info.md) | [Пользователь](user.md) | [Пользователь,](user.md) связанный с оповещением. [](alerts.md)

## <a name="properties"></a>Свойства

Свойство |    Тип    |    Описание
:---|:---|:---
id | Строка | ИД оповещения.
title | String | Заголовок оповещения.
description | String | Описание оповещения.
alertCreationTime | Nullable DateTimeOffset | Дата и время (в UTC) было создано оповещение.
lastEventTime | Nullable DateTimeOffset | Последнее событие, срабатывающее оповещением на том же устройстве.
firstEventTime | Nullable DateTimeOffset | Первое появление события, срабатывающее оповещением на этом устройстве.
lastUpdateTime | Nullable DateTimeOffset | Дата и время (в UTC) последнее обновление оповещений.
resolvedTime | Nullable DateTimeOffset | Дата и время, в течение которых состояние оповещений было изменено на "Разрешено".
incidentId | Nullable Long | [ИД](view-incidents-queue.md) оповещений об инциденте.
investigationId | Nullable Long | ID [исследования,](automated-investigations.md) связанный с оповещением.
investigationState | Nullable Enum | Текущее состояние [расследования](automated-investigations.md). Возможные значения: "Unknown", "Terminated", "SuccessfullyRemediated", 'Benign', 'Failed', 'PartiallyRemediated', "Running", "PendingApproval", "PendingResource", "PartiallyInvestigated", "TerminatedByUser", "TerminatedBySystem", "Queued", "InnerFailure", "PreexistingAlert", "UnsupportedAlert", "SuppressedAlert".
assignedTo | String | Владелец оповещений.
severity | Перечисление | Степень серьезности оповещения. Возможные значения: "UnSpecified", "Informational", "Low", "Medium" и "High".
status | Перечисление | Указывает текущее состояние оповещений. Возможные значения: "Unknown", "New", "InProgress" и "Resolved".
classification | Nullable Enum | Спецификация оповещений. Возможные значения: "Неизвестный", "FalsePositive", "TruePositive".
определение | Nullable Enum | Указывает определение оповещений. Возможные значения: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other".
category| String | Категория оповещения.
detectionSource | Строка | Источник обнаружения.
threatFamilyName | Строка | Семейство угроз.
threatName | Строка | Имя угрозы.
machineId | Строка | ID объекта [машины,](machine.md) связанного с оповещением.
computerDnsName | Строка | [полное](machine.md) имя машины.
aadTenantId | Строка | ID Azure Active Directory.
detectorId | Строка | ID детектора, который вызвал оповещение.
comments | Список замечаний оповещений | Объект Alert Comment содержит строку комментариев, createdBy string и createTime date time.
Свидетельство | Список доказательств оповещений | Доказательства, относящиеся к оповещению. См. приведенный ниже пример.

### <a name="response-example-for-getting-single-alert"></a>Пример ответа для получения единого оповещения:

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
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
}
```
