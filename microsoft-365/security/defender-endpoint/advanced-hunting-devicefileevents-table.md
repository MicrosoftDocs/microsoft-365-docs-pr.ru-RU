---
title: Таблица DeviceFileEvents в продвинутой схеме охоты
description: Узнайте о событиях, связанных с файлами, в таблице DeviceFileEvents продвинутой схемы охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, devicefileevents, files, path, hash, sha1, sha256, md5, FileCreationEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21a1bb17771314bc64f92009df4138e9550a7389
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075110"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Таблица `DeviceFileEvents` в [продвинутой схеме охоты](advanced-hunting-overview.md) содержит сведения о создании файлов, изменении и других событиях файловой системы. Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

Сведения о других таблицах в продвинутой схеме охоты см. в справке [о схеме охоты.](advanced-hunting-schema-reference.md)

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор устройства в службе |
| `DeviceName` | строка | Полное доменное имя (FQDN) устройства |
| `ActionType` | строка | Тип действий, которые вызвали событие |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FolderPath` | string | Папка, содержащая файл, к котором было применено записано действие |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `SHA256` | string | SHA-256 файла, к которому было применено записанное действие Это поле обычно не заполнено— используйте столбец SHA1 при наличии |
| `MD5` | строка | Hash MD5 файла, к который было применено записано действие |
| `FileOriginUrl` | строка | URL-адрес, в котором файл был загружен из |
| `FileOriginReferrerUrl` | строка | URL-адрес веб-страницы, ссылаемой на загруженный файл |
| `FileOriginIP` | строка | IP-адрес, на который был загружен файл с |
| `InitiatingProcessAccountDomain` | строка | Домен учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountName` | строка | Имя пользователя учетной записи, которая запустила процесс, ответственный за событие |
| `InitiatingProcessAccountSid` | строка | Идентификатор безопасности (SID) учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessMD5` | строка | AD5 hash of the process (image file), that initiated the event |
| `InitiatingProcessSHA1` | строка | SHA-1 процесса (файла изображений), который инициировал событие |
| `InitiatingProcessFolderPath` | строка | Папка, содержащая процесс (файл изображений), который инициировал событие |
| `InitiatingProcessFileName` | строка | Имя процесса, который инициировал событие |
| `InitiatingProcessId` | int | Процесс ID (PID) процесса, который инициировал событие |
| `InitiatingProcessCommandLine` | строка | Командная строка, используемая для запуска процесса, инициированного событием |
| `InitiatingProcessCreationTime` | datetime | Дата и время начала процесса запуска события |
| `InitiatingProcessIntegrityLevel` | строка | уровень целостности процесса, который инициировал событие. Windows назначает уровни целостности процессам, основанным на определенных характеристиках, например, если они были запущены из скачивания в Интернете. Эти уровни целостности влияют на разрешения на ресурсы |
| `InitiatingProcessTokenElevation` | строка | Тип маркера, указывающий на наличие или отсутствие высоты привилегий управления пользовательским доступом (UAC), применяемой к процессу, инициировал событие. |
| `InitiatingProcessParentId` | int | Process ID (PID) родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentFileName` | строка | Имя родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время запуска родительского процесса, ответственного за событие |
| `RequestProtocol` | строка | Сетевой протокол, если это применимо, используется для инициализа действия: Unknown, Local, SMB или NFS |
| `ShareName` | строка | Имя общей папки, содержащей файл |
| `RequestSourceIP` | строка | IPv4 или IPv6 адрес удаленного устройства, которое инициировало действие |
| `RequestSourcePort` | строка | Исходный порт на удаленном устройстве, которое инициировало действие |
| `RequestAccountName` | строка | Имя пользователя учетной записи, используемой для удаленного инициа- |
| `RequestAccountDomain` | строка | Домен учетной записи, используемой для удаленного инициа- |
| `RequestAccountSid` | строка | Идентификатор безопасности (SID) учетной записи для удаленного начала действия |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp. |
| `AppGuardContainerId` | строка | Идентификатор виртуализированного контейнера, используемого службой Application Guard для изоляции активности браузера |
| `SensitivityLabel` | строка | Метка, примененная к электронной почте, файлу или другому содержимому для классификации его для защиты информации |
| `SensitivitySubLabel` | строка | Sublabel применяется к электронной почте, файлу или другому контенту, чтобы классифицировать его для защиты информации; Подклабели чувствительности группироваться под метки чувствительности, но обрабатываются независимо |
| `IsAzureInfoProtectionApplied` | boolean | Указывает, шифруется ли файл в Azure Information Protection |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
