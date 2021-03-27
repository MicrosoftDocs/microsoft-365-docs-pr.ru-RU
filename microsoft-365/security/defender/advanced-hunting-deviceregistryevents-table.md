---
title: Таблица DeviceRegistryEvents в продвинутой схеме охоты
description: Узнайте о событиях реестра, которые можно запросить из таблицы DeviceRegistryEvents в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, registryevents, registry, DeviceRegistryEvents, key, subkey, value
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 129ed0340dc8324bfa8e68a9f5e1532f92262ac8
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382833"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица `DeviceRegistryEvents` в [продвинутой схеме](advanced-hunting-overview.md) охоты содержит сведения о создании и изменении записей реестра. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!TIP]
> Подробные сведения о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в центре безопасности.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `ActionType` | string | Тип действий, которые вызвали событие. Подробные [сведения см. в](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) справке по схеме на портале |
| `RegistryKey` | Строка | Ключ реестра, к который было применено записано действие |
| `RegistryValueType` | Строка | Тип данных, например двоичный или строковой, значения реестра, к которое было применено записанное действие |
| `RegistryValueName` | Строка | Имя значения реестра, к которое было применено записанное действие |
| `RegistryValueData` | Строка | Данные о значении реестра, которое было применено к зарегистрированным действиям |
| `PreviousRegistryKey` | Строка | Исходный ключ реестра значения реестра перед его изменением |
| `PreviousRegistryValueName` | Строка | Исходное имя значения реестра перед его изменением |
| `PreviousRegistryValueData` | Строка | Исходные данные значения реестра перед его изменением |
| `InitiatingProcessAccountDomain` | Строка | Домен учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountName` | Строка | Имя пользователя учетной записи, которая запустила процесс, ответственный за событие |
| `InitiatingProcessAccountSid` | Строка | Идентификатор безопасности (SID) учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountUpn` | Строка | Основное имя пользователя (UPN) учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountObjectId` | Строка | ID объекта Azure AD учетной записи пользователя, которая запустила процесс, ответственный за событие |
| `InitiatingProcessSHA1` | Строка | SHA-1 процесса (файла изображений), который инициировал событие |
| `InitiatingProcessSHA256` | Строка | SHA-256 процесса (файла изображений), который инициировал событие. Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `InitiatingProcessMD5` | string | AD5 hash of the process (image file), that initiated the event |
| `InitiatingProcessFileName` | Строка | Имя процесса, который инициировал событие |
| `InitiatingProcessFileSize` | long | Размер файла, который запустил процесс, ответственный за событие |
| `InitiatingProcessVersionInfoCompanyName` | Строка | Название компании из сведений о версии процесса (файла изображений), ответственного за событие |
| `InitiatingProcessVersionInfoProductName` | Строка | Имя продукта из сведений о версии процесса (файл изображений), ответственных за событие |
|` InitiatingProcessVersionInfoProductVersion` | Строка | Версия продукта из сведений о версии процесса (файла изображений), ответственного за событие |
|` InitiatingProcessVersionInfoInternalFileName` | Строка | Имя внутреннего файла из сведений о версии процесса (файла изображений), ответственного за событие |
| `InitiatingProcessVersionInfoOriginalFileName` | Строка | Исходное имя файла из версии данных процесса (файла изображений), ответственного за событие |
| `InitiatingProcessVersionInfoFileDescription` | Строка | Описание из сведений о версии процесса (файла изображений), ответственного за событие |
| `InitiatingProcessId` | int | Процесс ID (PID) процесса, который инициировал событие |
| `InitiatingProcessCommandLine` | Строка | Командная строка, используемая для запуска процесса, инициированного событием |
| `InitiatingProcessCreationTime` | datetime | Дата и время начала процесса запуска события |
| `InitiatingProcessFolderPath` | Строка | Папка, содержащая процесс (файл изображений), который инициировал событие |
| `InitiatingProcessParentId` | int | Process ID (PID) родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentFileName` | Строка | Имя родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время запуска родительского процесса, ответственного за событие |
| `InitiatingProcessIntegrityLevel` | Строка | Уровень целостности процесса, который инициировал событие. Windows назначает уровни целостности процессам, основанным на определенных характеристиках, например, если они были запущены из скачивания в Интернете. Эти уровни целостности влияют на разрешения на ресурсы |
| `InitiatingProcessTokenElevation` | Строка | Тип маркера, указывающий на наличие или отсутствие высоты привилегий управления пользовательским доступом (UAC), применяемой к процессу, инициировал событие. |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp. |
| `AppGuardContainerId` | Строка | Идентификатор виртуализированного контейнера, используемого службой Application Guard для изоляции активности браузера |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
