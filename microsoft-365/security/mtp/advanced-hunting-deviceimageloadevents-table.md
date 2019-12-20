---
title: Таблица девицеимажелоадевентс в схеме расширенного поискового окна
description: Сведения о загрузке DLL событий в таблице Девицеимажелоадевентс расширенной схемы подсистемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз, Поиск угроз, поиск, запрос, телеметрии, Справочник по схеме, Кусто, таблица, столбец, тип данных, описание, имажелоадевентс, Девицеимажелоадевентс, загрузка DLL, Библиотека, изображение файла
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: fdb69ee2e53372fdc486679831704c98202dddfe
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809383"
---
# <a name="deviceimageloadevents"></a>девицеимажелоадевентс

**Область применения:**
- Защита от угроз (Майкрософт)

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`DeviceImageLoadEvents` Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о событиях загрузки DLL. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

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
| `MD5` | string | Хэш MD5 файла, к которому было применено записанное действие |
| `InitiatingProcessAccountDomain` | string | Домен учетной записи, в которой выполнялся процесс, ответственный за событие. |
| `InitiatingProcessAccountName` | string | Имя пользователя учетной записи, в которой выполнялся процесс, ответственный за событие. |
| `InitiatingProcessAccountSid` | string | Идентификатор безопасности (SID) учетной записи, в которой выполнялся процесс, ответственный за событие. |
| `InitiatingProcessIntegrityLevel` | string | Уровень целостности процесса, который инициировал событие. Windows назначает уровни целостности процессам на основе определенных характеристик, например, если они были запущены при загрузке из Интернета. Эти уровни целостности влияют на разрешения для ресурсов |
| `InitiatingProcessTokenElevation` | string | Тип маркера, указывающий на присутствие или отсутствие повышения привилегий контроля доступа пользователей (UAC), примененного к процессу, который инициировал событие. |
| `InitiatingProcessSHA1` | string | SHA-1 процесса (файл изображения), который инициировал событие |
| `InitiatingProcessMD5` | string | Хеш MD5 для процесса (файла изображения), который инициировал событие |
| `InitiatingProcessFileName` | string | Имя процесса, который инициировал событие |
| `InitiatingProcessId` | int | Идентификатор процесса (PID), который инициировал событие |
| `InitiatingProcessCommandLine` | string | Командная строка, используемая для запуска процесса, который инициировал событие |
| `InitiatingProcessCreationTime` | datetime | Дата и время начала процесса, инициировавшего событие |
| `InitiatingProcessFolderPath` | string | Папка, содержащая процесс (файл изображения), который инициировал событие |
| `InitiatingProcessParentId` | int | Идентификатор процесса (PID) родительского процесса, который попытался выполнить процесс, ответственный за событие. |
| `InitiatingProcessParentFileName` | string | Имя родительского процесса, который попытался выполнить процесс, ответственный за событие. |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время начала родительского объекта процесса, ответственного за событие. |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец должен использоваться в сочетании со столбцами DeviceName и timestamp |
| `AppGuardContainerId` | string | Идентификатор виртуального контейнера, используемого Application Guard для изоляции активности браузера |

## <a name="related-topics"></a>См. также
- [Заблаговременный поиск угроз](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
