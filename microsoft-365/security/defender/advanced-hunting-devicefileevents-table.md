---
title: Таблица DeviceFileEvents в продвинутой схеме охоты
description: Узнайте о событиях, связанных с файлами, в таблице DeviceFileEvents продвинутой схемы охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, filecreationevents, DeviceFileEvents, files, path, hash, sha1, sha256, md5
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1b716a37aa39dffc8dc541335f42265ae47fe989
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023010"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender
- Microsoft Defender для конечной точки

Таблица `DeviceFileEvents` в [продвинутой схеме охоты](advanced-hunting-overview.md) содержит сведения о создании файлов, изменении и других событиях файловой системы. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!TIP]
> Подробные сведения о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в центре безопасности.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `ActionType` | string | Тип действий, которые вызвали событие. Подробные [сведения см. в](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) справке по схеме на портале |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FolderPath` | string | Папка, содержащая файл, к котором было применено записано действие |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `SHA256` | string | SHA-256 файла, к которому было применено записанное действие Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `MD5` | string | Hash MD5 файла, к который было применено записано действие |
| `FileOriginUrl` | Строка | URL-адрес, в котором файл был загружен из |
| `FileOriginReferrerUrl` | Строка | URL-адрес веб-страницы, ссылаемой на загруженный файл |
| `FileOriginIP` | Строка | IP-адрес, на который был загружен файл с |
| `PreviousFolderPath` | Строка | Оригинальная папка, содержащая файл перед примененным действием |
| `PreviousFileName` | Строка | Исходное имя файла, переименованного в результате действия |
| `FileSize` | long | Размер файла в bytes |
| `InitiatingProcessAccountDomain` | Строка | Домен учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountName` | Строка | Имя пользователя учетной записи, которая запустила процесс, ответственный за событие |
| `InitiatingProcessAccountSid` | Строка | Идентификатор безопасности (SID) учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountUpn` | Строка | Основное имя пользователя (UPN) учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountObjectId` | Строка | ID объекта Azure AD учетной записи пользователя, которая запустила процесс, ответственный за событие |
| `InitiatingProcessMD5` | Строка | AD5 hash of the process (image file), that initiated the event |
| `InitiatingProcessSHA1` | Строка | SHA-1 процесса (файла изображений), который инициировал событие |
| `InitiatingProcessSHA256` | Строка | SHA-256 процесса (файла изображений), который инициировал событие. Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `InitiatingProcessFolderPath` | string | Папка, содержащая процесс (файл изображений), который инициировал событие |
| `InitiatingProcessFileName` | Строка | Имя процесса, который инициировал событие |
| `InitiatingProcessFileSize` | long | Размер процесса (файла изображений), который инициировал событие |
| `InitiatingProcessVersionInfoCompanyName` | Строка | Название компании из сведений о версии процесса (файла изображений), ответственного за событие |
| `InitiatingProcessVersionInfoProductName` | Строка | Имя продукта из сведений о версии процесса (файл изображений), ответственных за событие |
|` InitiatingProcessVersionInfoProductVersion` | Строка | Версия продукта из сведений о версии процесса (файла изображений), ответственного за событие |
|` InitiatingProcessVersionInfoInternalFileName` | Строка | Имя внутреннего файла из сведений о версии процесса (файла изображений), ответственного за событие |
| `InitiatingProcessVersionInfoOriginalFileName` | Строка | Исходное имя файла из версии данных процесса (файла изображений), ответственного за событие |
| `InitiatingProcessVersionInfoFileDescription` | Строка | Описание из сведений о версии процесса (файла изображений), ответственного за событие |
| `InitiatingProcessId` | int | Процесс ID (PID) процесса, который инициировал событие |
| `InitiatingProcessCommandLine` | Строка | Командная строка, используемая для запуска процесса, инициированного событием |
| `InitiatingProcessCreationTime` | datetime | Дата и время начала процесса запуска события |
| `InitiatingProcessIntegrityLevel` | Строка | Уровень целостности процесса, который инициировал событие. Windows назначает уровни целостности процессам на основе определенных характеристик, например, если они были запущены из скачивания в Интернете. Эти уровни целостности влияют на разрешения на ресурсы |
| `InitiatingProcessTokenElevation` | Строка | Тип маркера, указывающий на наличие или отсутствие высоты привилегий управления пользовательским доступом (UAC), применяемой к процессу, инициировал событие. |
| `InitiatingProcessParentId` | int | Process ID (PID) родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentFileName` | Строка | Имя родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время запуска родительского процесса, ответственного за событие |
| `RequestProtocol` | Строка | Сетевой протокол, если это применимо, используется для инициализа действия: Unknown, Local, SMB или NFS |
| `RequestSourceIP` | Строка | IPv4 или IPv6 адрес удаленного устройства, которое инициировало действие |
| `RequestSourcePort` | Строка | Исходный порт на удаленном устройстве, которое инициировало действие |
| `RequestAccountName` | Строка | Имя пользователя учетной записи, используемой для удаленного инициа- |
| `RequestAccountDomain` | Строка | Домен учетной записи, используемой для удаленного инициа- |
| `RequestAccountSid` | Строка | Идентификатор безопасности (SID) учетной записи, используемой для удаленного начала действия |
| `ShareName` | Строка | Имя общей папки, содержащей файл |
| `InitiatingProcessFileSize` | long | Размер файла, который запустил процесс, ответственный за событие |
| `SensitivityLabel` | Строка | Метка, примененная к электронной почте, файлу или другому содержимому для классификации его для защиты информации |
| `SensitivitySubLabel` | Строка | Sublabel применяется к электронной почте, файлу или другому контенту, чтобы классифицировать его для защиты информации; Подклабели чувствительности группироваться под метки чувствительности, но обрабатываются независимо |
| `IsAzureInfoProtectionApplied` | boolean | Указывает, шифруется ли файл в Azure Information Protection |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp. |
| `AppGuardContainerId` | Строка | Идентификатор виртуализированного контейнера, используемого службой Application Guard для изоляции активности браузера |
| `AdditionalFields` | Строка | Дополнительные сведения об объекте или событии |
>[!NOTE]
> Сведения о hash файла всегда будут показаны, когда они доступны. Однако существует несколько возможных причин, по которым не удается вычислить SHA1, SHA256 или MD5. Например, файл может быть расположен в удаленном хранилище, заблокирован другим процессом, сжатым или помеченным как виртуальный. В этих сценариях информация о хаши файла отображается пустой.

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
