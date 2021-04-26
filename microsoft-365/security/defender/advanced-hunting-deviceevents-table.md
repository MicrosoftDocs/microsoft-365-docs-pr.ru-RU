---
title: Таблица DeviceEvents в продвинутой схеме охоты
description: Узнайте о антивирусе, брандмауэре и других типах событий в таблице событий разных устройств (DeviceEvents) продвинутой схемы охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, ссылка схемы, kusto, таблица, столбец, тип данных, события безопасности, антивирус, брандмауэр, защита эксплойта, DeviceEvents
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
ms.openlocfilehash: 63a2d41714329918192caccd384587a4e4f04112
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023205"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Microsoft 365 Defender
- Microsoft Defender для конечной точки

Различные события или таблицы устройств в схеме предварительной охоты содержат сведения о различных типах событий, в том числе событиях, инициированных средствами управления безопасностью, такими как Защитник Windows антивирус и защита от эксплойтов. `DeviceEvents` [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

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
| `FileSize` | long | Размер файла в bytes |
| `AccountDomain` | String | Домен учетной записи |
| `AccountName` | String | Имя пользователя учетной записи |
| `AccountSid` | String | Идентификатор безопасности (SID) учетной записи |
| `RemoteUrl` | string | URL-адрес или полное доменное имя, к которому выполнено подключение |
| `RemoteDeviceName` | string | Имя машины, которая выполняла удаленную операцию на пораженной машине. В зависимости от сообщаемого события это имя может быть полностью квалифицированным доменным именем (FQDN), именем NetBIOS или хост-именем без сведений о домене. |
| `ProcessId` | int | ID процесса (PID) вновь созданного процесса |
| `ProcessCommandLine` | String | Командная строка, используемая для создания нового процесса |
| `ProcessCreationTime` | datetime | Дата и время создания процесса |
| `ProcessTokenElevation` | String | Тип маркера, указывающий на наличие или отсутствие высоты привилегий управления доступом пользователей (UAC), применяемой к вновь созданному процессу |
| `LogonId` | String | Идентификатор для сеанса логотипа. Этот идентификатор уникален на одной машине только между перезапусками |
| `RegistryKey` | String | Ключ реестра, к который было применено записано действие |
| `RegistryValueName` | String | Имя значения реестра, к которое было применено записанное действие |
| `RegistryValueData` | String | Данные о значении реестра, которое было применено к зарегистрированным действиям |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `RemotePort` | int | TCP-порт на удаленном устройстве, подключенного к |
| `LocalIP` | String | IP-адрес, присвоенный локальной машине, используемой во время связи |
| `LocalPort` | int | Порт TCP на локальной машине, используемой во время связи |
| `FileOriginUrl` | String | URL-адрес, в котором файл был загружен из |
| `FileOriginIP` | String | IP-адрес, на который был загружен файл с |
| `InitiatingProcessSHA1` | String | SHA-1 процесса (файла изображений), который инициировал событие |
| `InitiatingProcessSHA256` | String | SHA-256 процесса (файла изображений), который инициировал событие. Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `InitiatingProcessMD5` | string | AD5 hash of the process (image file), that initiated the event |
| `InitiatingProcessFileName` | String | Имя процесса, который инициировал событие |
| `InitiatingProcessFileSize` | long | Размер файла, который запустил процесс, ответственный за событие |
| `InitiatingProcessFolderPath` | String | Папка, содержащая процесс (файл изображений), который инициировал событие |
| `InitiatingProcessId` | int | Процесс ID (PID) процесса, который инициировал событие |
| `InitiatingProcessCommandLine` | String | Командная строка, используемая для запуска процесса, инициированного событием |
| `InitiatingProcessCreationTime` | datetime | Дата и время начала процесса запуска события |
| `InitiatingProcessAccountDomain` | String | Домен учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountName` | String | Имя пользователя учетной записи, которая запустила процесс, ответственный за событие |
| `InitiatingProcessAccountSid` | String | Идентификатор безопасности (SID) учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountUpn` | String | Основное имя пользователя (UPN) учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountObjectId` | String | ID объекта Azure AD учетной записи пользователя, которая запустила процесс, ответственный за событие |
| `InitiatingProcessVersionInfoCompanyName` | String | Название компании из сведений о версии процесса (файла изображений), ответственного за событие |
| `InitiatingProcessVersionInfoProductName` | String | Имя продукта из сведений о версии процесса (файл изображений), ответственных за событие |
| `InitiatingProcessVersionInfoProductVersion` | String | Версия продукта из сведений о версии процесса (файла изображений), ответственного за событие |
|` InitiatingProcessVersionInfoInternalFileName` | String | Имя внутреннего файла из сведений о версии процесса (файла изображений), ответственного за событие |
| `InitiatingProcessVersionInfoOriginalFileName` | String | Исходное имя файла из версии данных процесса (файла изображений), ответственного за событие |
| `InitiatingProcessVersionInfoFileDescription` | String | Описание из сведений о версии процесса (файла изображений), ответственного за событие |
| `InitiatingProcessParentId` | int | Process ID (PID) родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentFileName` | String | Имя родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время запуска родительского процесса, ответственного за событие |
| `InitiatingProcessLogonId` | String | Идентификатор для сеанса логотипа процесса, который инициировал событие. Этот идентификатор уникален на одной машине только между перезапусками |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp. |
| `AppGuardContainerId` | String | Идентификатор виртуализированного контейнера, используемого службой Application Guard для изоляции активности браузера |
| `AdditionalFields` | String | Дополнительные сведения о событии в формате массива JSON |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
