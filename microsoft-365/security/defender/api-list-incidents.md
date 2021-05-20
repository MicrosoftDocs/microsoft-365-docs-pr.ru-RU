---
title: Список инцидентов API в Microsoft 365 Defender
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
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572157"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Список инцидентов API в Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.


## <a name="api-description"></a>Описание API

API списков инцидентов позволяет сортировать инциденты для создания обоснованных мер по кибербезопасности. Он предоставляет набор инцидентов, которые были отмечены в вашей сети, в течение определенного времени в политике удержания среды. Последние инциденты отображаются в верхней части списка. Каждый инцидент содержит массив связанных оповещений и связанных с ними сущностей.

API поддерживает следующих **операторов OData:**

- `$filter` на `lastUpdateTime` `createdTime` , `status` , и `assignedTo` свойства
- `$top`, с максимальным значением **100**
- `$skip`

## <a name="limitations"></a>Ограничения

1. Максимальный размер страницы **составляет 100 инцидентов.**
2. Максимальная скорость запросов **составляет 50 звонков в минуту** **и 1500 звонков в час.**

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Чтобы узнать больше, в том числе как выбрать разрешения, смотрите [API Microsoft 365 Access Microsoft 365 Defender](api-access.md)

Тип разрешения | Разрешение | Имя дисплея разрешения
-|-|-
Приложение | Инцидент.Read.All | Прочитайте все инциденты
Приложение | Инцидент.ReadWrite.All | Читать и писать все инциденты
Делегированное (рабочая или учебная учетная запись) | Инцидент.Читайте | Читать инциденты
Делегированное (рабочая или учебная учетная запись) | Инцидент.ReadWrite | Инциденты чтения и записи

> [!Note]
> При получении токена с использованием учетных данных пользователя:
>
> - Пользователь должен иметь разрешение на просмотр инцидентов на портале.
> - Ответ будет включать только инциденты, с которые пользователь подвергается.

## <a name="http-request"></a>HTTP-запрос

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
-|-|-
Authorization | String | Носитель (токен). **Required**


## <a name="request-body"></a>Текст запроса

Нет.

## <a name="response"></a>Отклик

В случае успеха, этот метод `200 OK` возвращается, и список [инцидентов](api-incident.md) в органе реагирования.

## <a name="schema-mapping"></a>Схема отображение

### <a name="incident-metadata"></a>Метаданные инцидентов

Имя поля | Описание | Пример значения
-|-|-
инцидентИд | Уникальный идентификатор для представления инцидента | 924565
перенаправитьИдентид | Только населенные в случае инцидента в настоящее время сгруппированы вместе с другим инцидентом, как часть логики обработки инцидентов. | 924569
инцидентИмя | Значение строки, доступное для каждого инцидента. | Действия программы-шантажиста.
созданTime | Время, когда инцидент был впервые создан. | 2020-09-06T14:46:57.0733333
lastUpdateTime | Время, когда инцидент был в последний раз обновлен на бэкэнде.<br /><br /> Это поле может быть использовано при настройке параметра запроса на диапазон времени извлечения инцидентов. | 2020-09-06T14:46:57.29
assignedTo | Владелец инцидента, или *нулевой,* если владелец не назначен. | secop2@contoso.com
classification | Спецификация инцидента. Значения свойств: Неизвестный *,* *FalsePositive*, *TruePositive* | Unknown
решимость | Уточняется определение инцидента. Значения свойств: *Недоступно, Apt*, *Вредоносные* *программы*, *SecurityPersonnel*, *SecurityTesting*, *НежелательныеСофтвейд*, *Другие* | Недоступно
status | Категоризация инцидентов (как *Active*, или *Разрешено).* Это может помочь вам организовать и управлять вашим ответом на инциденты. | Активна
severity | Указывает на возможное влияние на активы. Чем выше тяжесть, тем больше воздействие. Обычно элементы более высокой степени тяжести требуют самого пристального внимания.<br /><br />Одно из следующих значений: *Информационное,* *Низкое,*«Среднее» и *«Высокое».* | Средний
tags | Массив пользовательских тегов, связанных с инцидентом, например, чтобы пометить группу инцидентов с общей характеристикой. | \[\]
comments | Множество комментариев, созданных secops при управлении инцидентом, например дополнительная информация о выборе классификации. | \[\]
alerts | Массив, содержащий все оповещения, связанные с инцидентом, а также другую информацию, такую как серьезность, сущности, которые были вовлечены в оповещение, и источник предупреждений. | \[\] (см. подробную информацию о полях оповещения ниже)

### <a name="alerts-metadata"></a>Оповещения метаданных

Имя поля | Описание | Пример значения
-|-|-
alertId | Уникальный идентификатор для представления оповещения | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
инцидентИд | Уникальный идентификатор для представления инцидента, с который связано это предупреждение | 924565
сервисИсточник | Служба, от которого исходит оповещение, например, Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity или Microsoft Defender для Office 365. | MicrosoftCloudAppБезопасность
созданиеTime | Время, когда предупреждение было впервые создано. | 2020-09-06T14:46:55.7182276
последнееУченное время | Время последнего обновления оповещения в бэкэнде. | 2020-09-06T14:46:57.2433333
решеноTime | Время, когда тревога была решена. | 2020-09-10T05:22:59
firstActivity | Время, когда оповещение впервые сообщило, что активность была обновлена в бэкэнде.| 2020-09-04T05:22:59
title | Краткое определение значения строки, доступного для каждого предупреждения. | Действия программы-шантажиста.
description | Значение строки, описывающее каждое оповещение. | Пользователь Test User2 (testUser2@contoso.com) манипулировал 99 файлами с несколькими расширениями, *заканчивающимся необычным расширением herunterladen.* Это необычное количество манипуляций с файлами и свидетельствует о потенциальной атаке вымогателей.
category | Визуальное и числовое представление о том, как далеко продвинулась атака по цепочке убийства. Приведены в [соответствие с рамками&CK™ MITRE.](https://attack.mitre.org/) | Влияние
status | Категоризация оповещений *(как новые,* *активные* или *разрешены).* Это может помочь вам организовать и управлять вашим ответом на оповещения. | Новая
severity | Указывает на возможное влияние на активы. Чем выше тяжесть, тем больше воздействие. Обычно элементы более высокой степени тяжести требуют самого пристального внимания.<br>Одно из следующих значений: *Информационное,* *Низкое,*«Среднее» и *«Высокое».* | Средний
investigationId | Автоматизированное удостоверение личности расследования, вызванное этим предупреждением. | 1234
расследованиеГосударство | Информация о текущем состоянии следствия. Одно из следующих значений: *Неизвестный*, *Прекращено*, *УспешноВосстановлено* *,* Доброкачественные *,* Не удалось *,* *ЧастичноВосстановленный*, Запуск , *PendingApproval*, *PendingResource*, *ЧастичноInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Очередь*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, НеподдерживаемыйAlertType , *Подавленный.*  | НеподдерживаемыйАлертТип
classification | Спецификация инцидента. Значения свойств: Неизвестный *,* *FalsePositive*, *TruePositive*, или *нулевой* | Unknown
решимость | Уточняется определение инцидента. Значения свойств: *Недоступно, Apt* *,* *Вредоносные программы*, *SecurityPersonnel*, *SecurityTesting*, *НежелательныеСофтвейд*, *Другие или* *нулевой* | способный
assignedTo | Владелец инцидента, или *нулевой,* если владелец не назначен. | secop2@contoso.com
актерИмя | Группа действий, если таковые имеются, связанная с этим предупреждением. | бор
угрозаСемейнаяимя | Семейство угроз, связанное с этим предупреждением. | null
mitreTechniques | Методы атаки, как приведены в [соответствие с CK&CK](https://attack.mitre.org/)™ CK. | \[\]
приборы | Все устройства, на которых были отправлены оповещения, связанные с инцидентом. | \[\] (см. подробную информацию о полях сущности ниже)

### <a name="device-format"></a>Формат устройства

Имя поля | Описание | Пример значения
-|-|-
УстройствоИд | Идентификатор устройства, указанный в Microsoft Defender для конечной точки. | 24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId |  Идентификатор устройства, указанный в [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis). Доступно только для устройств, подключенных к домену. | null
устройствоДнсНайм | Полностью квалифицированное доменное имя для устройства. | user5cx.middleeast.corp.contoso.com
osPlatform | Платформа ОС, на которую работает устройство.| WindowsServer2016
osBuild | Версия сборки для ОС, которую использует устройство. | 14393
rbacGroupName | Группа [управления доступом на основе](/azure/role-based-access-control/overview) роли (RBAC), связанная с устройством. | WDATP-Ring0
первыйSeen | Время, когда устройство было впервые замечено. | 2020-02-06T14:16:01.9330135
healthStatus | Состояние здоровья устройства. | Активна
рискСкор | Оценка риска для устройства. | Высокая
Объекты | Все организации, которые были определены как часть или связанные с данным предупреждением. | \[\] (см. подробную информацию о полях сущности ниже)

### <a name="entity-format"></a>Формат сущности

Имя поля | Описание | Пример значения
-|-|-
entityType | Организации, которые были определены как часть или связанные с данным предупреждением.<br>Значения свойств: Пользователь *,* *Ip*, Url , *Файл*, *Процесс* *,* *MailBox*, *MailMessage*, *MailCluster*, *реестр* | Пользователь
sha1 | Доступно, если entityType является *файл*.<br>Хэш файла для оповещений, связанных с файлом или процессом. | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256 | Доступно, если entityType является *файл*.<br>Хэш файла для оповещений, связанных с файлом или процессом. | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
fileName | Доступно, если entityType является *файл*.<br>Название файла для оповещений, связанных с файлом или процессом | Detector.UnitTests.dll
filePath | Доступно, если entityType является *файл*.<br>Путь файла для оповещений, связанных с файлом или процессом | C: \\ «agent_work_temp» Развертывание»SYSTEM»2020-09-06 12-14-54
processId | Доступно, если entityType является *процесс*. | 24348
процессКомандЛайн | Доступно, если entityType является *процесс*. | "Ваш файл готов к загрузке \_1911150169.exe"
processCreationTime | Доступно, если entityType является *процесс*. | 2020-07-18T03:25:38.5269993
parentProcessId | Доступно, если entityType является *процесс*. | 16840
parentProcessCreationTime | Доступно, если entityType является *процесс*. | 2020-07-18T02:12:32.8616797
ipAddress | Доступно, если entityType *является Ip*. <br>IP-адрес для оповещений, связанных с сетевыми событиями, *таких как связь с вредоносным сетевым пунктом назначения.* | 62.216.203.204
url | Доступно, если entityType *является Url*. <br>Url для оповещений, связанных с сетевыми событиями, *такими как, Связь с вредоносным сетевым пунктом назначения.* | down.esales360.cn
accountName | Доступно, если entityType является *пользователем*. | testUser2
domainName | Доступно, если entityType является *пользователем*. | europe.corp.contoso
пользовательСид | Доступно, если entityType является *пользователем*. | S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId | Доступно, если entityType является *пользователем*. | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | Доступно, если entityType *является* / *пользователем* / *MailBox MailMessage*. | testUser2@contoso.com
почтовый ящикДисплейНайм | Доступно, если entityType *является MailBox*. | тест Пользователя2
почтовый ящикАдресуйт | Доступно, если entityType *является* / *пользователем* / *MailBox MailMessage*. | testUser2@contoso.com
кластерБай | Доступно, если entityType  *является MailCluster*. | Тема; P2SenderDomain; СодержаниеТип
sender | Доступно, если entityType *является* / *пользователем* / *MailBox MailMessage*. | user.abc@mail.contoso.co.in
получатель; | Доступно, если entityType *является MailMessage*. | testUser2@contoso.com
subject | Доступно, если entityType *является MailMessage*. | \[EXTERNAL \] Внимание
доставка Действий | Доступно, если entityType *является MailMessage*. | доставленный
securityGroupId | Доступно, если entityType  *является SecurityGroup*. | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName | Доступно, если entityType  *является SecurityGroup*. | Операторы конфигурации сети
registryHive | Доступно, если entityType является  *реестр*. | МЕСТНАЯ \_ МАШИНА \_ HKEY |
registryKey | Доступно, если entityType является  *реестр*. | SOFTWARE-Microsoft Windows NT CurrentVersion-Winlogon
registryValueType | Доступно, если entityType является  *реестр*. | String
registryValue | Доступно, если entityType является  *реестр*. | 31-00-00-00
deviceId | Идентификатор устройства, если таковые имеются, связанный с сущностью. | 986e5df8b73d43c8917d17e523e76b13c75cd

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

- [Доступ к Microsoft 365-имуме защитника](api-access.md)
- [Узнайте об ограничениях API и лицензировании](api-terms.md)
- [Понимание кодов ошибок](api-error-codes.md)
- [Обзор инцидентов](incidents-overview.md)
- [Программные интерфейсы, относящиеся к инцидентам](api-incident.md)
- [Обновление API инцидента](api-update-incidents.md)
