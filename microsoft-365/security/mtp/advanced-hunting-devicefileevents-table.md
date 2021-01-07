---
title: Таблица DeviceFileEvents в схеме advanced hunting
description: Узнайте о событиях, связанных с файлами, в таблице DeviceFileEvents схемы advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, fileFileEvents, files, path, hash, sha1, sha256, md5
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 9b48321693f883e40a100e29e5e1ec3c5203caa2
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771863"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица в схеме advanced hunting содержит сведения о создании, изменении файлов и других `DeviceFileEvents` событиях файловой [](advanced-hunting-overview.md) системы. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

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
| `FileOriginUrl` | Строка | URL-адрес для скачивания файла |
| `FileOriginReferrerUrl` | Строка | URL-адрес веб-страницы, ссылаемой на скачаный файл |
| `FileOriginIP` | Строка | IP-адрес, с которых был загружен файл |
| `InitiatingProcessAccountDomain` | Строка | Домен учетной записи, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessAccountName` | Строка | Имя пользователя учетной записи, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessAccountSid` | Строка | Идентификатор безопасности (SID) учетной записи, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessMD5` | Строка | AD5 hash of the process (image file) that initiated the event |
| `InitiatingProcessSHA1` | Строка | SHA-1 процесса (файла изображения), который инициировал событие |
| `InitiatingProcessSHA256` | Строка | SHA-256 процесса (файла изображения), который инициировал событие. Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `InitiatingProcessFolderPath` | string | Папка, содержащая процесс (файл изображения), который инициировал событие |
| `InitiatingProcessFileName` | Строка | Имя процесса, который инициировал событие |
| `InitiatingProcessId` | int | ИД процесса, который инициировал событие |
| `InitiatingProcessCommandLine` | Строка | Командная строка, используемая для запуска процесса, который инициировал событие |
| `InitiatingProcessCreationTime` | datetime | Дата и время запуска процесса, который инициировал событие |
| `InitiatingProcessIntegrityLevel` | Строка | Уровень целостности процесса, который инициировал событие. Windows назначает уровни целостности процессам на основе определенных характеристик, например, если они были запущены из скачивания из Интернета. Эти уровни целостности влияют на разрешения для ресурсов |
| `InitiatingProcessTokenElevation` | Строка | Тип маркера, указывающий на наличие или отсутствие повышения привилегий контроля доступа пользователей (UAC), примененного к процессу, который инициировал событие |
| `InitiatingProcessParentId` | int | ИД (PID) родительского процесса, который ил процесса, ответственного за событие |
| `InitiatingProcessParentFileName` | Строка | Имя родительского процесса, который ил процесса, ответственного за событие |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время начала родительского процесса, ответственного за событие |
| `RequestProtocol` | Строка | Сетевой протокол, если применимо, используется для инициализируемых действий: Unknown, Local, SMB или NFS |
| `ShareName` | Строка | Имя общей папки, содержащей файл |
| `RequestSourceIP` | Строка | IPv4- или IPv6-адрес удаленного устройства, которое инициировало действие |
| `RequestSourcePort` | Строка | Исходный порт на удаленном устройстве, которое инициировало действие |
| `RequestAccountName` | Строка | Имя пользователя учетной записи, используемой для удаленного инициирования действия |
| `RequestAccountDomain` | Строка | Домен учетной записи, используемой для удаленного инициировать действие |
| `RequestAccountSid` | Строка | Идентификатор безопасности (SID) учетной записи, используемой для удаленного инициирования действия |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец необходимо использовать вместе со столбцами DeviceName и Timestamp. |
| `AppGuardContainerId` | Строка | Идентификатор виртуализированного контейнера, используемого Application Guard для изоляции активности браузера |
| `SensitivityLabel` | Строка | Метка, примененная к сообщению электронной почты, файлу или другому содержимому для классификации для защиты информации |
| `SensitivitySubLabel` | Строка | Вложенная пометь, примененная к электронному, файлу или другому содержимому, чтобы классифицировать ее для защиты информации; в подчиненной метки конфиденциальности группироваться по метки конфиденциальности, но обрабатываются независимо |
| `IsAzureInfoProtectionApplied` | boolean | Указывает, шифруется ли файл службой Azure Information Protection |

>[!NOTE]
> Сведения о hash-файле всегда будут показываться, когда они доступны. Однако существует несколько возможных причин, по которым не удается вычислить SHA1, SHA256 или MD5. Например, файл может быть расположен в удаленном хранилище, заблокирован другим процессом, сжат или помечен как виртуальный. В этих сценариях информация о hash-файле отображается пустой.

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
