---
title: Таблица DeviceProcessEvents в схеме advanced hunting
description: Узнайте о событиях создания или создания процесса в DeviceProcessEventstable схемы расширенных охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, processcreationevents, DeviceProcessEvents, process id, command line, DeviceProcessEvents
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
ms.openlocfilehash: 6f94b861aa73d01f9e906d41bc52a9724552cd33
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145515"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender



Таблица `DeviceProcessEvents` в схеме [advanced hunting](advanced-hunting-overview.md) содержит сведения о создании процессов и связанных событиях. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

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
| `ProcessId` | int | ИД процесса (PID) только что созданного процесса |
| `ProcessCommandLine` | string | Командная строка, используемая для создания нового процесса |
| `ProcessIntegrityLevel` | string | Уровень целостности только что созданного процесса. Windows назначает уровни целостности процессам на основе определенных характеристик, например, если они были запущены из скачаного интернета. Эти уровни целостности влияют на разрешения для ресурсов |
| `ProcessTokenElevation` | string | Указывает тип повышения прав маркера, примененного к только что созданному процессу. Возможные значения: TokenElevationTypeLimited (restricted), TokenElevationTypeDefault (стандартный) и TokenElevationTypeFull (с повышенными уровнями) |
| `ProcessCreationTime` | datetime | Дата и время создания процесса |
| `AccountDomain` | string | Домен учетной записи |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `AccountUpn` | string | Имя пользователя-пользователя (UPN) учетной записи |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure AD |
| `LogonId` | string | Идентификатор сеанса logon. Этот идентификатор уникален на одном компьютере только между перезапусками |
| `InitiatingProcessAccountDomain` | string | Домен учетной записи, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessAccountName` | string | Имя пользователя учетной записи, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessAccountSid` | string | Идентификатор безопасности (SID) учетной записи, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessAccountUpn` | string | Имя пользователя-пользователя (UPN) учетной записи, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessAccountObjectId` | string | ИД объекта Azure AD учетной записи пользователя, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessLogonId` | string | Идентификатор сеанса для процесса, который инициировал событие. Этот идентификатор уникален на одном компьютере только между перезапусками. |
| `InitiatingProcessIntegrityLevel` | string | Уровень целостности процесса, который инициировал событие. Windows назначает уровни целостности процессам на основе определенных характеристик, например, если они были запущены из скачивания из Интернета. Эти уровни целостности влияют на разрешения для ресурсов |
| `InitiatingProcessTokenElevation` | string | Тип маркера, указывающий на наличие или отсутствие повышения привилегий контроля доступа пользователей (UAC), примененного к процессу, который инициировал событие |
| `InitiatingProcessSHA1` | string | SHA-1 процесса (файла изображения), который инициировал событие |
| `InitiatingProcessSHA256` | string | SHA-256 процесса (файла изображения), который инициировал событие. Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `InitiatingProcessMD5` | string | Hash MD5 процесса (файл изображения), который инициировал событие |
| `InitiatingProcessFileName` | string | Имя процесса, который инициировал событие |
| `InitiatingProcessFileSize` | long | Размер файла, который запустил процесс, отвечающий за событие |
| `InitiatingProcessId` | int | ИД процесса, который инициировал событие |
| `InitiatingProcessCommandLine` | string | Командная строка, используемая для запуска процесса, который инициировал событие |
| `InitiatingProcessCreationTime` | datetime | Дата и время запуска процесса, который инициировал событие |
| `InitiatingProcessFolderPath` | string | Папка, содержащая процесс (файл изображения), который инициировал событие |
| `InitiatingProcessParentId` | int | ИД (PID) родительского процесса, который ил процесса, ответственного за событие |
| `InitiatingProcessParentFileName` | string | Имя родительского процесса, который ил процесса, ответственного за событие |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время начала родительского процесса, ответственного за событие |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец необходимо использовать вместе со столбцами DeviceName и Timestamp. |
| `AppGuardContainerId` | string | Идентификатор виртуализированного контейнера, используемого Application Guard для изоляции активности браузера |
| `AdditionalFields` | string | Дополнительные сведения о событии в формате массива JSON |
| `FileSize` | long | Размер файла в ветвях |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
