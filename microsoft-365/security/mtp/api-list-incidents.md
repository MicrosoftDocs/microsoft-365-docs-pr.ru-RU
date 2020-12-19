---
title: API списка инцидентов в Microsoft 365 Defender
description: Список API инцидентов в Microsoft 365 Defender
keywords: список, инцидент, инциденты, api
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
ms.openlocfilehash: 13508d3ad9d61797517ccb55a27152883947843a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719432"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>API списка инцидентов в Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>Описание API

API инцидентов списков позволяет сортировать инциденты, чтобы создать информированный ответ на кибербезопасность. Он предоставляет коллекцию инцидентов, которые были помечены в сети в течение указанного вами диапазона времени в политике хранения среды. Последние инциденты отображаются в верхней части списка. Каждый инцидент содержит массив связанных оповещений и связанных с ними сущностями.

API поддерживает следующие **операторы OData:**

- `$filter`в `lastUpdateTime` `createdTime` свойствах , `status` , и `assignedTo`
- `$top`, с максимальным значением **100**
- `$skip`

## <a name="limitations"></a>Ограничения

1. Максимальный размер страницы составляет **100 инцидентов.**
2. Максимальная скорость запросов составляет **50 вызовов в минуту** и **1500 вызовов в час.**

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные возможности, включая выбор разрешений, см. в [API Access в Microsoft 365 Defender](api-access.md)

Тип разрешения | Разрешение | Отображаемая имя разрешения
-|-|-
Приложение | Incident.Read.All | Чтение всех инцидентов
Приложение | Incident.ReadWrite.All | Чтение и написание всех инцидентов
Делегированные (рабочая или учебная учетная запись) | Incident.Read | Чтение инцидентов
Делегированные (рабочая или учебная учетная запись) | Incident.ReadWrite | Чтение и написание инцидентов

> [!Note]
> При получении маркера с использованием учетных данных пользователя:
>
> - Пользователь должен иметь разрешение на просмотр инцидентов на портале.
> - Ответ будет включать только инциденты, с которые пользователь может получить данные.

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

В случае успеха этот метод возвращает список инцидентов в `200 OK` теле ответа. [](api-incident.md)

## <a name="schema-mapping"></a>Сопоставление схемы

### <a name="incident-metadata"></a>Метаданные инцидента

Имя поля | Описание | Пример значения
-|-|-
incidentId | Уникальный идентификатор для представления инцидента | 924565
redirectIncidentId | Заполняется только в том случае, если инцидент сгруппировали вместе с другим инцидентом в рамках логики обработки инцидента. | 924569
incidentName | Строка, доступная для каждого инцидента. | Действия программы-вымогателя
createdTime | Время создания инцидента. | 2020-09-06T14:46:57.073333Z
lastUpdateTime | Время последнего обновления инцидента на тыловом сайте.<br /><br /> Это поле можно использовать при настройке параметра запроса в течение диапазона времени, в течение времени, в течение который извлекаются инциденты. | 2020-09-06T14:46:57.29Z
assignedTo | Владелец инцидента или *null,* если владелец не назначен. | secop2@contoso.com
classification | Спецификация инцидента. Значения свойств: *Unknown,* *FalsePositive,* *TruePositive* | Unknown
определение | Определяет определение инцидента. Значения свойств: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* | NotAvailable
status | Классифицировать инциденты (как *активные* или *разрешенные).* Это поможет вам организовать реагирование на инциденты и управлять ими. | Активное
severity | Указывает возможное влияние на ресурсы. Чем выше степень серьезности, тем больше это влияние. Как правило, элементы с более высокой степенью серьезности требуют непосредственного внимания.<br /><br />Одно из следующих значений: *Informational,* *Low,**Medium и *High.* | Средняя
tags | Массив пользовательских тегов, связанных с инцидентом, например для пометки группы инцидентов с общей характеристикой. | \[\]
alerts | Массив, содержащий все оповещения, связанные с инцидентом, а также другие сведения, такие как серьезность, объекты, задействованные в оповещении, и источник оповещений. | \[\] (См. сведения о полях оповещений ниже)

### <a name="alerts-metadata"></a>Метаданные оповещений

Имя поля | Описание | Пример значения
-|-|-
alertId | Уникальный идентификатор для представления оповещения | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId | Уникальный идентификатор для представления инцидента, с котором связано данное оповещение | 924565
serviceSource | Служба, от которую исходит оповещение, например Microsoft Defender для конечной точки, Microsoft Cloud App Security, Microsoft Defender для удостоверений или Microsoft Defender для Office 365. | MicrosoftCloudAppSecurity
creationTime | Время создания оповещения. | 2020-09-06T14:46:55.7182276Z
lastUpdatedTime | Время последнего обновления оповещения на тыловом уровне. | 2020-09-06T14:46:57.2433333Z
resolvedTime | Время разрешения оповещения. | 2020-09-10T05:22:59Z
firstActivity | Время, когда оповещение впервые сообщило об обновлении активности на тыловой части.| 2020-09-04T05:22:59Z
title | Краткое определение строки, доступной для каждого оповещения. | Действия программы-вымогателя
description | Строка, описывающие каждое оповещение. | Пользователь Test User2 (testUser2@contoso.com) с помощью 99 файлов с несколькими расширениями, заканчивающийся на редкое расширение *herunterladen.* Это необычное количество манипуляций с файлами, что свидетельствует о возможной атаке программы-вымогателя.
category | Визуальное и числовое представление о том, как далеко идет атака по цепочке атак. Соответствует структуре [MITRE ATT&CK™](https://attack.mitre.org/). | Влияние
status | Классифицировать оповещения *(например, "Новый",* *"Активный"* или *"Разрешено").* Это поможет вам упорядоизировать и управлять ответами на оповещения. | Новое
severity | Указывает возможное влияние на ресурсы. Чем выше степень серьезности, тем больше это влияние. Как правило, элементы с более высокой степенью серьезности требуют непосредственного внимания.<br>Одно из следующих значений: *Informational,* *Low,**Medium и *High.* | Средняя
investigationId | ИД автоматического исследования, инициированный этим оповещением. | 1234
investigationState | Сведения о текущем состоянии исследования. Одно из следующих значений: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedAlertType*, *SuppressedAlert*.  | UnsupportedAlertType
classification | Спецификация инцидента. Значения свойств: *Unknown,* *FalsePositive,* *TruePositive* или *null* | Unknown
определение | Определяет определение инцидента. Значения свойств: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* или  *null* | Apt
assignedTo | Владелец инцидента или *null,* если владелец не назначен. | secop2@contoso.com
actorName | Группа действий, если она есть, связанная с этим оповещением. | ВАЗОН
threatFamilyName | Семейство угроз, связанное с этим оповещением. | null
mitreTechniques | Методы атаки в соответствие с решением [MITRE ATT](https://attack.mitre.org/)&CK ™ CK. | \[\]
устройства | Все устройства, на которые были отправлены оповещения, связанные с инцидентом. | \[\] (см. сведения о полях суностей ниже)

### <a name="device-format"></a>Формат устройства

Имя поля | Описание | Пример значения
-|-|-
DeviceId | ИД устройства, указанный в ATP в Microsoft Defender. | 24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId |  ИД устройства, назначенный в [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) Доступно только для устройств, которые присоединились к домену. | null
deviceDnsName | Полное доменное имя устройства. | user5cx.middleeast.corp.contoso.com
osPlatform | Платформа ОС, запущенная на устройстве.| WindowsServer2016
osBuild | Версия сборки для ОС, запущенной на устройстве. | 14393
rbacGroupName | Группа [управления доступом](https://docs.microsoft.com/azure/role-based-access-control/overview) на основе ролей (RBAC), связанная с устройством. | WDATP-Ring0
firstSeen | Время первого увидеть устройство. | 2020-02-06T14:16:01.9330135Z
healthStatus | Состояние состояния состояния устройства. | Активное
riskScore | Оценка риска для устройства. | Высокий
entities | Все сущности, которые были определены как часть или связанные с заданным оповещением. | \[\] (см. сведения о полях суностей ниже)

### <a name="entity-format"></a>Формат сущности

Имя поля | Описание | Пример значения
-|-|-
entityType | Сущности, которые определены как часть заданного оповещения или связаны с ним.<br>Значения свойств: *User*, *Ip*, *URL*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry* | Пользователь
sha1 | Доступно, если entityType имеет *тип File.*<br>Hash файла для оповещений, связанных с файлом или процессом. | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256 | Доступно, если entityType имеет *тип File.*<br>Hash файла для оповещений, связанных с файлом или процессом. | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
fileName | Доступно, если entityType имеет *тип File.*<br>Имя файла оповещений, связанных с файлом или процессом | Detector.UnitTests.dll
filePath | Доступно, если entityType имеет *тип File.*<br>Путь к файлу для оповещений, связанных с файлом или процессом | C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
processId | Доступно, если entityType является *Process*. | 24348
processCommandLine | Доступно, если entityType — *"Процесс".* | "Ваш файл готов к загрузке \_1911150169.exe"
processCreationTime | Доступно, если entityType — *"Процесс".* | 2020-07-18T03:25:38.5269993Z
parentProcessId | Доступно, если entityType — *"Процесс".* | 16840
parentProcessCreationTime | Доступно, если entityType — *"Процесс".* | 2020-07-18T02:12:32.8616797Z
ipAddress | Доступно, если entityType *имеет ip.* <br>IP-адрес для оповещений, связанных с сетевыми событиями, такими как *связь с вредоносным сетевым адресом.* | 62.216.203.204
url | Доступно, если entityType имеет *URL-адрес.* <br>URL-адрес оповещений, связанных с сетевыми событиями, например, *"Связь с вредоносным сетевым пунктом назначения".* | down.esales360.cn
accountName | Доступно, если entityType — *пользователь.* | testUser2
domainName | Доступно, если entityType — *пользователь.* | europe.corp.contoso
userSid | Доступно, если entityType — *пользователь.* | S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId | Доступно, если entityType — *пользователь.* | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | Доступно, если entityType —  /  / *mailMessage* почтового ящика пользователя. | testUser2@contoso.com
mailboxDisplayName | Доступно, если entityType — *MailBox.* | test User2
mailboxAddress | Доступно, если entityType —  /  / *mailMessage* почтового ящика пользователя. | testUser2@contoso.com
clusterBy | Доступно, если entityType — *MailCluster.* | Тема; P2SenderDomain; ContentType
sender | Доступно, если entityType —  /  / *mailMessage* почтового ящика пользователя. | user.abc@mail.contoso.co.in
получатель; | Доступно, если entityType — *MailMessage.* | testUser2@contoso.com
subject | Доступно, если entityType — *MailMessage.* | \[ВНЕШНЕЕ \] внимание
deliveryAction | Доступно, если entityType — *MailMessage.* | Доставлено
securityGroupId | Доступно, если entityType имеет *тип SecurityGroup.* | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName | Доступно, если entityType имеет *тип SecurityGroup.* | Операторы конфигурации сети
registryHive | Доступно, если entityType имеет *тип Registry.* | ЛОКАЛЬНЫЙ КОМПЬЮТЕР HKEY \_ \_ |
registryKey | Доступно, если entityType имеет *тип Registry.* | SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registryValueType | Доступно, если entityType имеет *тип Registry.* | String
registryValue | Доступно, если entityType имеет *тип Registry.* | 31-00-00-00
deviceId | ИД устройства, связанного с сущностью( если он имеется). | 986e5df8b73dacd43c8917d17e523e76b13c75cd

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

## <a name="related-articles"></a>Статьи по теме

- [Доступ к API Microsoft 365 Defender](api-access.md)
- [Узнайте об ограничениях API и лицензировании](api-terms.md)
- [Коды ошибок](api-error-codes.md)
- [Обзор инцидентов](incidents-overview.md)
- [Программные интерфейсы, относящиеся к инцидентам](api-incident.md)
- [Обновление API инцидентов](api-update-incidents.md)
