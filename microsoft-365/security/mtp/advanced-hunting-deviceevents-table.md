---
title: Таблица DeviceEvents в схеме advanced hunting
description: Узнайте о антивирусной программы, брандмауэре и других типах событий в таблице событий разных устройств (DeviceEvents) схемы расширенных охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, security events, antivirus, firewall, exploit guard, DeviceEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1340464fbe71e919a60668cf7d1b2f535eb6d260
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145329"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender



Различные события или таблицы устройств в схеме advanced hunting содержат сведения о различных типах событий, в том числе событиях, инициированных средствами управления безопасностью, такими как защита от вирусов Защитник Windows и защита от `DeviceEvents` эксплойтов. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!TIP]
> Для получения подробных сведений о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в Центре безопасности. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).


| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `ActionType` | string | Тип действия, которое вызвало событие. Подробные сведения см. в справке [по схеме портала](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FolderPath` | string | Папка, содержащая файл, к которой было применено записано действие |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `SHA256` | string | SHA-256 файла, к которому было применено записанное действие Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `MD5` | string | MD5 hash of the file that the recorded action was applied to |
| `AccountDomain` | string | Домен учетной записи |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `RemoteUrl` | string | URL-адрес или полное доменное имя, к которому выполнено подключение |
| `RemoteDeviceName` | string | Имя компьютера, который выполнил удаленную операцию на затронутом компьютере. В зависимости от сообщаемого события это имя может быть полное доменное имя, netBIOS-имя или имя хоста без сведений о домене. |
| `ProcessId` | int | ИД процесса (PID) только что созданного процесса |
| `ProcessCommandLine` | string | Командная строка, используемая для создания нового процесса |
| `ProcessCreationTime` | datetime | Дата и время создания процесса |
| `ProcessTokenElevation` | string | Тип маркера, указывающий на наличие или отсутствие повышения привилегий контроля доступа пользователей (UAC), примененного к созданному процессу |
| `LogonId` | string | Идентификатор сеанса logon. Этот идентификатор уникален на одном компьютере только между перезапусками |
| `RegistryKey` | string | Ключ реестра, к который было применено записано действие |
| `RegistryValueName` | string | Имя значения реестра, к которое было применено записанное действие |
| `RegistryValueData` | string | Данные значения реестра, к которое было применено записано действие |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `RemotePort` | int | TCP-порт на удаленном устройстве, к |
| `LocalIP` | string | IP-адрес, присвоенный локальному компьютеру, используемму во время связи |
| `LocalPort` | int | TCP-порт на локальном компьютере, используемом во время связи |
| `FileOriginUrl` | string | URL-адрес для скачивания файла |
| `FileOriginIP` | string | IP-адрес, с которых был загружен файл |
| `AdditionalFields` | string | Дополнительные сведения о событии в формате массива JSON |
| `InitiatingProcessFileSize` | long | Размер файла, который запустил процесс, отвечающий за событие |
| `FileSize` | long | Размер файла в ветвях |
| `InitiatingProcessSHA1` | string | SHA-1 процесса (файла изображения), который инициировал событие |
| `InitiatingProcessSHA256` | string | SHA-256 процесса (файла изображения), который инициировал событие. Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `InitiatingProcessFileName` | string | Имя процесса, который инициировал событие |
| `InitiatingProcessFolderPath` | string | Папка, содержащая процесс (файл изображения), который инициировал событие |
| `InitiatingProcessId` | int | ИД процесса, который инициировал событие |
| `InitiatingProcessCommandLine` | string | Командная строка, используемая для запуска процесса, который инициировал событие |
| `InitiatingProcessCreationTime` | datetime | Дата и время начала процесса, инициа |
| `InitiatingProcessParentId` | int | ИД (PID) родительского процесса, который ил процесса, ответственного за событие |
| `InitiatingProcessParentFileName` | string | Имя родительского процесса, который ил процесса, ответственного за событие |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время начала родительского процесса, ответственного за событие |
| `InitiatingProcessMD5` | string | AD5 hash of the process (image file) that initiated the event |
| `InitiatingProcessAccountDomain` | string | Домен учетной записи, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessAccountName` | string | Имя пользователя учетной записи, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessAccountSid` | string | Идентификатор безопасности (SID) учетной записи, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessAccountUpn` | string | Имя пользователя-пользователя (UPN) учетной записи, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessAccountObjectId` | string | ИД объекта Azure AD учетной записи пользователя, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessLogonId` | string | Идентификатор сеанса для процесса, который инициировал событие. Этот идентификатор уникален на одном компьютере только между перезапусками |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp |
| `AppGuardContainerId` | string | Идентификатор виртуализированного контейнера, используемого Application Guard для изоляции активности браузера |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
