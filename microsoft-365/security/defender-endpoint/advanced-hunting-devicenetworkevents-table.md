---
title: Таблица DeviceNetworkEvents в продвинутой схеме охоты
description: Узнайте о событиях подключения к сети, которые можно запросить в таблице DeviceNetworkEvents в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, devicenetworkevents, network connection, remote ip, local ip, NetworkCommunicationEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: de31cb923a0584f45cb92340cf7e1c6b5ca5e9a0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500774"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Таблица `DeviceNetworkEvents` в [продвинутой схеме охоты](advanced-hunting-overview.md) содержит сведения о сетевых подключениях и связанных событиях. Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

Сведения о других таблицах в продвинутой схеме охоты см. в справке [о схеме охоты.](advanced-hunting-schema-reference.md)

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор устройства в службе |
| `DeviceName` | string | Полное доменное имя (FQDN) устройства |
| `ActionType` | string | Тип действий, которые вызвали событие |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `RemotePort` | int | TCP-порт на удаленном устройстве, подключенного к |
| `RemoteUrl` | string | URL-адрес или полное доменное имя, к которому выполнено подключение |
| `LocalIP` | string | IP-адрес, присвоенный локальному устройству, используемму во время связи |
| `LocalPort` | int | Порт TCP на локальном устройстве, используемом во время связи |
| `Protocol` | string | Используемый протокол IP, будь то TCP или UDP |
| `LocalIPType` | string | Тип IP-адресов, например public, Private, Reserved, Loopback, Teredo, FourToSixMapping и Broadcast |
| `RemoteIPType` | string | Тип IP-адресов, например public, Private, Reserved, Loopback, Teredo, FourToSixMapping и Broadcast |
| `InitiatingProcessSHA1` | string | SHA-1 процесса (файла изображений), который инициировал событие |
| `InitiatingProcessMD5` | string | AD5 hash of the process (image file), that initiated the event |
| `InitiatingProcessFileName` | string | Имя процесса, который инициировал событие |
| `InitiatingProcessId` | int | Процесс ID (PID) процесса, который инициировал событие |
| `InitiatingProcessCommandLine` | string | Командная строка, используемая для запуска процесса, инициированного событием |
| `InitiatingProcessCreationTime` | datetime | Дата и время начала процесса запуска события |
| `InitiatingProcessFolderPath` | string | Папка, содержащая процесс (файл изображений), который инициировал событие |
| `InitiatingProcessParentFileName` | string | Имя родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentId` | int | Process ID (PID) родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время запуска родительского процесса, ответственного за событие |
| `InitiatingProcessAccountDomain` | string | Домен учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountName` | string | Имя пользователя учетной записи, которая запустила процесс, ответственный за событие |
| `InitiatingProcessAccountSid` | string | Идентификатор безопасности (SID) учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessIntegrityLevel` | string | Уровень целостности процесса, который инициировал событие. Windows назначает уровни целостности процессам, основанным на определенных характеристиках, например, если они были запущены из скачивания в Интернете. Эти уровни целостности влияют на разрешения на ресурсы |
| `InitiatingProcessTokenElevation` | string | Тип маркера, указывающий на наличие или отсутствие высоты привилегий управления пользовательским доступом (UAC), применяемой к процессу, инициировал событие. |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец должен использоваться совместно с `DeviceName` `Timestamp` столбцами и |
| `AppGuardContainerId` | string | Идентификатор виртуализированного контейнера, используемого службой Application Guard для изоляции активности браузера |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
