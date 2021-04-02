---
title: Таблица DeviceEvents в продвинутой схеме охоты
description: Узнайте о антивирусе, брандмауэре и других типах событий в таблице событий разных устройств (DeviceEvents) продвинутой схемы охоты
keywords: продвинутая охота, охота на угрозы, поиск, запрос, телеметрия, справочная схема, кусто, таблица, столбец, тип данных, события безопасности, антивирус, брандмауэр, охрана эксплойтов, MiscEvents
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
ms.openlocfilehash: 1e67da3a5d93c5e8c86afd755c882f3f0459aab0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499200"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Различные события или таблицы устройств в схеме предварительной охоты содержат сведения о различных типах событий, включая события, инициированные средствами безопасности, такими как антивирус Microsoft Defender и защита от `DeviceEvents` эксплойтов. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

Сведения о других таблицах в продвинутой схеме охоты см. в справке [о схеме охоты.](advanced-hunting-schema-reference.md)

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор устройства в службе |
| `DeviceName` | string | Полное доменное имя (FQDN) устройства |
| `ActionType` | string | Тип действий, которые вызвали событие |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FolderPath` | string | Папка, содержащая файл, к котором было применено записано действие |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `SHA256` | string | SHA-256 файла, к которому было применено записанное действие Это поле обычно не заполнено— используйте столбец SHA1 при наличии |
| `MD5` | string | Hash MD5 файла, к который было применено записано действие |
| `AccountDomain` | string | Домен учетной записи |
| `AccountName` |string | Имя пользователя учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `RemoteUrl` | string | URL-адрес или полное доменное имя, к которому выполнено подключение |
| `RemoteDeviceName` | string | Имя устройства, которое выполняло удаленную операцию на затронутом устройстве. В зависимости от сообщаемого события это имя может быть полностью квалифицированным доменным именем (FQDN), именем NetBIOS или хост-именем без сведений о домене. |
| `ProcessId` | int | ID процесса (PID) вновь созданного процесса |
| `ProcessCommandLine` | string | Командная строка, используемая для создания нового процесса |
| `ProcessCreationTime` | datetime | Дата и время создания процесса |
| `ProcessTokenElevation` | string | Тип маркера, указывающий на наличие или отсутствие высоты привилегий управления доступом пользователей (UAC), применяемой к вновь созданному процессу |
| `LogonId` | string | Идентификатор для сеанса логотипа. Этот идентификатор уникален на одном устройстве только между перезапусками |
| `RegistryKey` | string | Ключ реестра, к который было применено записано действие |
| `RegistryValueName` | string | Имя значения реестра, к которое было применено записанное действие |
| `RegistryValueData` | string | Данные о значении реестра, которое было применено к зарегистрированным действиям |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `RemotePort` | int | TCP-порт на удаленном устройстве, подключенного к |
| `LocalIP` | string | IP-адрес, присвоенный локальному устройству, используемму во время связи |
| `LocalPort` | int | Порт TCP на локальном устройстве, используемом во время связи |
| `FileOriginUrl` | string | URL-адрес, в котором файл был загружен из |
| `FileOriginIP` | string | IP-адрес, на который был загружен файл с |
| `AdditionalFields` | string | Дополнительные сведения о событии в формате массива JSON |
| `InitiatingProcessSHA1` | string | SHA-1 процесса (файла изображений), который инициировал событие |
| `InitiatingProcessSHA256` | string | SHA-256 процесса (файла изображений), который инициировал событие. Это поле обычно не заполнено— используйте столбец SHA1 при наличии |
| `InitiatingProcessFileName` | string | Имя процесса, который инициировал событие |
| `InitiatingProcessFolderPath` | string | Папка, содержащая процесс (файл изображений), который инициировал событие |
| `InitiatingProcessId` | int | Процесс ID (PID) процесса, который инициировал событие |
| `InitiatingProcessCommandLine` | string | Командная строка, используемая для запуска процесса, инициированного событием |
| `InitiatingProcessCreationTime` | datetime | Дата и время начала процесса запуска события |
| `InitiatingProcessParentId` | int | Process ID (PID) родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentFileName` | string | Имя родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время запуска родительского процесса, ответственного за событие |
| `InitiatingProcessMD5` | string | AD5 hash of the process (image file), that initiated the event |
| `InitiatingProcessAccountDomain` | string | Домен учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountName` | string | Имя пользователя учетной записи, которая запустила процесс, ответственный за событие |
| `InitiatingProcessAccountSid` | string | Идентификатор безопасности (SID) учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessLogonId` | string | Идентификатор для сеанса логотипа процесса, который инициировал событие. Этот идентификатор уникален на одном устройстве только между перезапусками |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец должен использоваться совместно с `DeviceName` `Timestamp` столбцами и |
| `AppGuardContainerId` | string | Идентификатор виртуализированного контейнера, используемого службой Application Guard для изоляции активности браузера |


## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
