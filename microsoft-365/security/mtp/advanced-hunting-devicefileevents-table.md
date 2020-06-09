---
title: Таблица девицефиливентс в схеме расширенного поискового окна
description: Сведения о событиях, связанных с файлами, в таблице Девицефиливентс расширенной схемы поиске
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, филекреатионевентс, Девицефиливентс, файлы, путь, хэш, SHA1, SHA256, MD5
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4b815afbe8e3ca1f7967d13f6482b90f7c64e362
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617166"
---
# <a name="devicefileevents"></a>DeviceFileEvents

**Область применения:**
- Защита от угроз (Майкрософт)

`DeviceFileEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о создании, изменении и других событиях файловой системы. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `ActionType` | string | Тип действия, вызвавшего событие |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FolderPath` | string | Папка, содержащая файл, к которому было применено записанное действие |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `SHA256` | string | SHA-256 файла, к которому было применено записанное действие Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `MD5` | string | Хэш MD5 файла, к которому было применено записанное действие |
| `FileOriginUrl` | string | URL-адрес, с которого был загружен файл |
| `FileOriginReferrerUrl` | string | URL-адрес веб-страницы, которая ссылается на скачанный файл |
| `FileOriginIP` | string | IP-адрес, с которого был загружен файл |
| `InitiatingProcessAccountDomain` | string | Домен учетной записи, в которой выполнялся процесс, ответственный за событие. |
| `InitiatingProcessAccountName` | string | Имя пользователя учетной записи, в которой выполнялся процесс, ответственный за событие. |
| `InitiatingProcessAccountSid` | string | Идентификатор безопасности (SID) учетной записи, в которой выполнялся процесс, ответственный за событие. |
| `InitiatingProcessMD5` | string | Хеш MD5 для процесса (файла изображения), который инициировал событие |
| `InitiatingProcessSHA1` | string | SHA-1 процесса (файл изображения), который инициировал событие |
| `InitiatingProcessSHA256` | string | SHA-256 процесса (файл изображения), который инициировал событие. Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `InitiatingProcessFolderPath` | string | Папка, содержащая процесс (файл изображения), который инициировал событие |
| `InitiatingProcessFileName` | string | Имя процесса, который инициировал событие |
| `InitiatingProcessId` | int | Идентификатор процесса (PID), который инициировал событие |
| `InitiatingProcessCommandLine` | string | Командная строка, используемая для запуска процесса, который инициировал событие |
| `InitiatingProcessCreationTime` | datetime | Дата и время начала процесса, инициировавшего событие |
| `InitiatingProcessIntegrityLevel` | string | Уровень целостности процесса, который инициировал событие. Windows назначает уровни целостности процессам на основе определенных характеристик, например, если они были запущены при загрузке из Интернета. Эти уровни целостности влияют на разрешения для ресурсов |
| `InitiatingProcessTokenElevation` | string | Тип маркера, указывающий на присутствие или отсутствие повышения привилегий контроля доступа пользователей (UAC), примененного к процессу, который инициировал событие. |
| `InitiatingProcessParentId` | int | Идентификатор процесса (PID) родительского процесса, который попытался выполнить процесс, ответственный за событие. |
| `InitiatingProcessParentFileName` | string | Имя родительского процесса, который попытался выполнить процесс, ответственный за событие. |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время начала родительского объекта процесса, ответственного за событие. |
| `RequestProtocol` | string | Сетевой протокол (при наличии), используемый для запуска действия: Unknown, Local, SMB или NFS |
| `ShareName` | string | Имя общей папки, содержащей файл |
| `RequestSourceIP` | string | IPv4-или IPv6-адрес удаленного устройства, инициировавшего действие |
| `RequestSourcePort` | string | Порт источника на удаленном устройстве, который инициировал действие |
| `RequestAccountName` | string | Имя пользователя учетной записи, используемой для удаленного запуска действия |
| `RequestAccountDomain` | string | Домен учетной записи, используемой для удаленного запуска действия |
| `RequestAccountSid` | string | Идентификатор безопасности (SID) учетной записи, используемой для удаленного запуска действия. |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец должен использоваться в сочетании со столбцами DeviceName и timestamp |
| `AppGuardContainerId` | string | Идентификатор виртуального контейнера, используемого Application Guard для изоляции активности браузера |
| `SensitivityLabel` | string | Метка, примененная к электронной почте, файлу или другому контенту, чтобы классифицировать ее для защиты информации |
| `SensitivitySubLabel` | string | Подметка, примененная к электронной почте, файлу или другому контенту, чтобы классифицировать ее для защиты информации; Подметки чувствительности группируются в соответствии с метками конфиденциальности, но обрабатываются независимо |
| `IsAzureInfoProtectionApplied` | boolean | Указывает, шифруется ли файл службой Azure Information Protection |

## <a name="related-topics"></a>Статьи по теме
- [Заблаговременный поиск угроз](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)