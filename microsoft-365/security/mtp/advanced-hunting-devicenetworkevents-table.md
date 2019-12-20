---
title: Таблица девиценетворкевентс в схеме расширенного поискового окна
description: Сведения о событиях сетевого подключения, которые можно запросить из таблицы Девиценетворкевентс расширенной схемы поиска
keywords: Расширенный поиск, Поиск угроз, Поиск угроз, Поиск угроз кибератак, поиск, запрос, телеметрии, Справочник по схеме, Кусто, таблица, столбец, тип данных, девиценетворкевентс, Нетворккоммуникатионевентс, сетевое подключение, удаленный IP-адрес, локальный IP-адрес
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
ms.openlocfilehash: 82475ad15090250aa4fca70a6810cb869128102d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809395"
---
# <a name="devicenetworkevents"></a>девиценетворкевентс

**Область применения:**
- Защита от угроз (Майкрософт)

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`DeviceNetworkEvents` Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о сетевых подключениях и связанных событиях. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `ActionType` | string | Тип действия, вызвавшего событие |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `RemotePort` | int | TCP-порт на удаленном устройстве, к которому было выполнено подключение |
| `RemoteUrl` | string | URL-адрес или полное доменное имя, к которому выполнено подключение |
| `LocalIP` | string | IP-адрес, назначенный локальному компьютеру, используемому при обмене данными |
| `LocalPort` | int | TCP-порт на локальном компьютере, используемый во время обмена данными |
| `Protocol` | string | Используемый протокол IP, TCP или UDP |
| `LocalIPType` | string | Тип IP-адреса, например общедоступный, частный, зарезервированный, петлевой, Teredo, Фауртосиксмаппинг и Broadcast |
| `RemoteIPType` | string | Тип IP-адреса, например общедоступный, частный, зарезервированный, петлевой, Teredo, Фауртосиксмаппинг и Broadcast |
| `InitiatingProcessSHA1` | string | SHA-1 процесса (файл изображения), который инициировал событие |
| `InitiatingProcessMD5` | string | Хеш MD5 для процесса (файла изображения), который инициировал событие |
| `InitiatingProcessFileName` | string | Имя процесса, который инициировал событие |
| `InitiatingProcessId` | int | Идентификатор процесса (PID), который инициировал событие |
| `InitiatingProcessCommandLine` | string | Командная строка, используемая для запуска процесса, который инициировал событие |
| `InitiatingProcessCreationTime` | datetime | Дата и время начала процесса, инициировавшего событие |
| `InitiatingProcessFolderPath` | string | Папка, содержащая процесс (файл изображения), который инициировал событие |
| `InitiatingProcessParentFileName` | string | Имя родительского процесса, который попытался выполнить процесс, ответственный за событие. |
| `InitiatingProcessParentId` | int | Идентификатор процесса (PID) родительского процесса, который попытался выполнить процесс, ответственный за событие. |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время начала родительского объекта процесса, ответственного за событие. |
| `InitiatingProcessAccountDomain` | string | Домен учетной записи, в которой выполнялся процесс, ответственный за событие. |
| `InitiatingProcessAccountName` | string | Имя пользователя учетной записи, в которой выполнялся процесс, ответственный за событие. |
| `InitiatingProcessAccountSid` | string | Идентификатор безопасности (SID) учетной записи, в которой выполнялся процесс, ответственный за событие. |
| `InitiatingProcessIntegrityLevel` | string | Уровень целостности процесса, который инициировал событие. Windows назначает уровни целостности процессам на основе определенных характеристик, например, если они были запущены при загрузке из Интернета. Эти уровни целостности влияют на разрешения для ресурсов |
| `InitiatingProcessTokenElevation` | string | Тип маркера, указывающий на присутствие или отсутствие повышения привилегий контроля доступа пользователей (UAC), примененного к процессу, который инициировал событие. |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец должен использоваться в сочетании со столбцами DeviceName и timestamp |
| `AppGuardContainerId` | string | Идентификатор виртуального контейнера, используемого Application Guard для изоляции активности браузера |

## <a name="related-topics"></a>См. также
- [Заблаговременный поиск угроз](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
