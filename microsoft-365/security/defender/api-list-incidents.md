---
title: API инцидентов списка в Microsoft 365 Defender
description: Узнайте, как перечислить API инцидентов в Microsoft 365 Defender
keywords: список, инциденты, инциденты, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 833bc1d8284829323cc2f0c391e42f4e563a6948
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730886"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>API инцидентов списка в Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.


## <a name="api-description"></a>Описание API

API инцидентов списка позволяет сортировать инциденты, чтобы создать обоснованный ответ на кибербезопасность. Он предоставляет коллекцию инцидентов, которые были помечены в сети, в диапазоне времени, указанном в политике хранения среды. Последние инциденты отображаются в верхней части списка. Каждый инцидент содержит массив связанных оповещений и связанных с ними сущностями.

API поддерживает следующих **операторов OData:**

- `$filter` на `lastUpdateTime` `createdTime` свойствах и `status` `assignedTo` свойствах
- `$top`с максимальным значением **100**
- `$skip`

## <a name="limitations"></a>Ограничения

1. Максимальный размер страницы **— 100 инцидентов.**
2. Максимальная скорость запросов — **50 вызовов в минуту** и **1500 вызовов в час.**

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные возможности, в том числе выбор разрешений, см. в Microsoft 365 [API Defender](api-access.md)

Тип разрешения | Разрешение | Имя отображения разрешений
-|-|-
Приложение | Incident.Read.All | Чтение всех инцидентов
Приложение | Incident.ReadWrite.All | Чтение и написание всех инцидентов
Делегированные (рабочая или учебная учетная запись) | Incident.Read | Чтение инцидентов
Делегированные (рабочая или учебная учетная запись) | Incident.ReadWrite | Чтение и написание инцидентов

> [!Note]
> При получении маркера с помощью учетных данных пользователей:
>
> - Пользователь должен иметь разрешение просмотра инцидентов на портале.
> - Ответ будет включать только инциденты, с которые пользователь подвергается действию.

## <a name="http-request"></a>HTTP-запрос

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
-|-|-
Авторизация | String | Bearer {token}. **Required**


## <a name="request-body"></a>Текст запроса

Нет.

## <a name="response"></a>Отклик

В случае успешной работы этот метод возвращается и список инцидентов `200 OK` в теле [](api-incident.md) отклика.

## <a name="schema-mapping"></a>Сопоставление схемы

### <a name="incident-metadata"></a>Метаданные инцидента

Имя поля | Описание | Пример значения
-|-|-
incidentId | Уникальный идентификатор для представления инцидента | 924565
redirectIncidentId | Заполняется только в том случае, если инцидент сгруппировали вместе с другим инцидентом, как часть логики обработки инцидента. | 924569
incidentName | Строковая стоимость, доступная для каждого инцидента. | Действия программы-шантажиста.
createdTime | Время создания инцидента. | 2020-09-06T14:46:57.0733333Z
lastUpdateTime | Время последнего обновления инцидента на задней части.<br /><br /> Это поле можно использовать при настройке параметра запроса для диапазона времени получения инцидентов. | 2020-09-06T14:46:57.29Z
assignedTo | Владелец инцидента или *null,* если не назначен владелец. | secop2@contoso.com
classification | Спецификация инцидента. Значения свойств: *Неизвестный,* *FalsePositive,* *TruePositive* | Unknown
определение | Указывает определение инцидента. Значения свойств: *NotAvailable*, *Apt*, *Вредоносные* программы , *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Другие* | NotAvailable
status | Классифицировать инциденты *(как Active* или *Resolved).* Это поможет вам организовать и управлять реагированием на инциденты. | Активация
severity | Указывает возможное влияние на активы. Чем больше серьезность, тем больше влияние. Как правило, элементы с более высокой степенью серьезности требуют непосредственного внимания.<br /><br />Одно из следующих значений: *Informational,* *Low*, *Medium и *High*. | Средний
tags | Массив пользовательских тегов, связанных с инцидентом, например для флага группы инцидентов с общей характеристикой. | \[\]
comments | Массив комментариев, созданных секопами при управлении инцидентом, например дополнительные сведения о выборе классификации. | \[\]
alerts | Массив, содержащий все оповещения, связанные с инцидентом, а также другие сведения, такие как серьезность, объекты, которые были вовлечены в оповещение, и источник оповещений. | \[\] (см. сведения о полях оповещений ниже)

### <a name="alerts-metadata"></a>Оповещения метаданных

Имя поля | Описание | Пример значения
-|-|-
alertId | Уникальный идентификатор для представления оповещений | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId | Уникальный идентификатор для представления инцидента, с котором связано это оповещение | 924565
serviceSource | Служба, откуда исходит оповещение, например Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity или Microsoft Defender для Office 365. | MicrosoftCloudAppSecurity
creationTime | Время создания оповещений. | 2020-09-06T14:46:55.7182276Z
lastUpdatedTime | Время последнего обновления оповещений в задней части. | 2020-09-06T14:46:57.2433333Z
resolvedTime | Время, когда оповещение было разрешено. | 2020-09-10T05:22:59Z
firstActivity | Время, когда оповещение впервые сообщило об обновлении активности в задней части.| 2020-09-04T05:22:59Z
title | Краткое определение строки, доступной для каждого оповещения. | Действия программы-шантажиста.
description | Строковая величина, описываемая каждое оповещение. | Пользователь Test User2 (testUser2@contoso.com) манипулировал 99 файлами с несколькими расширениями, заканчивающийся необычным *расширением herunterladen*. Это необычное количество манипуляций с файлами и указывает на потенциальную атаку вымогателей.
category | Визуальное и числовое представление о том, как далеко продвинулась атака по цепочке убийств. Согласовано с [структурой ATT MITRE&CK™](https://attack.mitre.org/). | Влияние
status | Классификация оповещений *(как New,* *Active* или *Resolved).* Это может помочь вам организовать и управлять вашим ответом на оповещения. | Новое
severity | Указывает возможное влияние на активы. Чем больше серьезность, тем больше влияние. Как правило, элементы с более высокой степенью серьезности требуют непосредственного внимания.<br>Одно из следующих значений: *Informational,* *Low*, *Medium и *High*. | Средний
investigationId | Автоматический ИД расследования, срабатываем этим оповещением. | 1234
investigationState | Сведения о текущем состоянии расследования. Одно из следующих *значений:* Unknown *,* Terminated , *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedAlertType*, *SuppressedAlert*.  | UnsupportedAlertType
classification | Спецификация инцидента. Значения свойств: *Неизвестный,* *FalsePositive,* *TruePositive* или *null* | Unknown
определение | Указывает определение инцидента. Значения свойств: *NotAvailable*, *Apt*, *Вредоносные* программы , *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Другие* или  *null* | Apt
assignedTo | Владелец инцидента или *null,* если не назначен владелец. | secop2@contoso.com
actorName | Группа действий, если таково, связанная с этим оповещением. | BORON
threatFamilyName | Семейство угроз, связанное с этим оповещением. | null
mitreTechniques | Методы атаки, в соответствие с структурой [ATT MITRE&CK](https://attack.mitre.org/)™. | \[\]
устройства | Все устройства, на которых были отправлены оповещения, связанные с инцидентом. | \[\] (см. сведения о полях сущности ниже)

### <a name="device-format"></a>Формат устройства

Имя поля | Описание | Пример значения
-|-|-
DeviceId | ID устройства, указанный в Microsoft Defender для конечной точки. | 24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId |  ID устройства, указанный в [Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-whatis) Доступно только для устройств, присоединимых к домену. | null
deviceDnsName | Полное доменное имя для устройства. | user5cx.middleeast.corp.contoso.com
osPlatform | Платформа ОС, на которой работает устройство.| WindowsServer2016
osBuild | Версия сборки для ОС, запущенная устройством. | 14393
rbacGroupName | Группа [управления доступом](/azure/role-based-access-control/overview) на основе ролей (RBAC), связанная с устройством. | WDATP-Ring0
firstSeen | Время, когда устройство было впервые замечено. | 2020-02-06T14:16:01.9330135Z
healthStatus | Состояние здоровья устройства. | Активация
riskScore | Оценка риска для устройства. | Фишинговое сообщение с
сущности | Все сущностями, которые были идентифицированы как часть или связанные с данным оповещением. | \[\] (см. сведения о полях сущности ниже)

### <a name="entity-format"></a>Формат сущности

Имя поля | Описание | Пример значения
-|-|-
entityType | Объекты, которые были идентифицированы как часть или связанные с данным оповещением.<br>Значения *свойств:* Пользователь , *Ip*, *URL*, *файл*, *процесс* *,* Почтовый ящик , *MailMessage*, *MailCluster*, *реестр* | Пользователь.
sha1 | Доступно, если entityType — *файл.*<br>Hash файла для оповещений, связанных с файлом или процессом. | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6ddd
sha256 | Доступно, если entityType — *файл.*<br>Hash файла для оповещений, связанных с файлом или процессом. | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
fileName | Доступно, если entityType — *файл.*<br>Имя файла для оповещений, связанных с файлом или процессом | Detector.UnitTests.dll
filePath | Доступно, если entityType — *файл.*<br>Путь к файлам для оповещений, связанных с файлом или процессом | C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
processId | Доступно, если entityType — *процесс.* | 24348
processCommandLine | Доступно, если entityType — *процесс.* | "Файл готов к загрузке \_1911150169.exe"
processCreationTime | Доступно, если entityType — *процесс.* | 2020-07-18T03:25:38.5269993Z
parentProcessId | Доступно, если entityType — *процесс.* | 16840
parentProcessCreationTime | Доступно, если entityType — *процесс.* | 2020-07-18T02:12:32.8616797Z
ipAddress | Доступно, если entityType *— ip.* <br>IP-адрес для оповещений, связанных с сетевыми событиями, такими как *связь с вредоносным сетевым назначением.* | 62.216.203.204
url | Доступно, если entityType *— url.* <br>URL-адрес для оповещений, связанных с сетевыми событиями, такими как Сообщение *с вредоносным сетевым назначением.* | down.esales360.cn
accountName | Доступно, если entityType — *пользователь.* | testUser2
domainName | Доступно, если entityType — *пользователь.* | europe.corp.contoso
userSid | Доступно, если entityType — *пользователь.* | S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId | Доступно, если entityType — *пользователь.* | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | Доступно, если entityType *— это почтовый* / *ящик* / *пользователя MailMessage.* | testUser2@contoso.com
mailboxDisplayName | Доступно, если entityType — *это MailBox.* | test User2
mailboxAddress | Доступно, если entityType *— это почтовый* / *ящик* / *пользователя MailMessage.* | testUser2@contoso.com
clusterBy | Доступно, если entityType *— это MailCluster.* | Subject; P2SenderDomain; ContentType
sender | Доступно, если entityType *— это почтовый* / *ящик* / *пользователя MailMessage.* | user.abc@mail.contoso.co.in
получатель; | Доступно, если entityType *— это MailMessage.* | testUser2@contoso.com
subject | Доступно, если entityType *— это MailMessage.* | \[ВНЕШНЕЕ \] внимание
deliveryAction | Доступно, если entityType *— это MailMessage.* | Доставлено
securityGroupId | Доступно, если entityType — *это SecurityGroup.* | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName | Доступно, если entityType — *это SecurityGroup.* | Операторы конфигурации сети
registryHive | Доступно, если entityType *является реестром.* | ЛОКАЛЬНЫЙ КОМПЬЮТЕР \_ HKEY \_ |
registryKey | Доступно, если entityType *является реестром.* | SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registryValueType | Доступно, если entityType *является реестром.* | String
registryValue | Доступно, если entityType *является реестром.* | 31-00-00-00
deviceId | ID, если таково, устройства, связанного с объектом. | 986e5df8b73dacd43c8917d17e523e76b13c75cd

## <a name="example"></a>Пример

**Запрос**

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

**Отклик**

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a>Связанные статьи

- [Доступ к API Microsoft 365 Defender](api-access.md)
- [Узнайте о ограничениях API и лицензировании](api-terms.md)
- [Понимание кодов ошибок](api-error-codes.md)
- [Обзор инцидентов](incidents-overview.md)
- [Программные интерфейсы, относящиеся к инцидентам](api-incident.md)
- [Обновление API инцидента](api-update-incidents.md)
