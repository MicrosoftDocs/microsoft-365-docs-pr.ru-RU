---
title: Таблица DeviceLogonEvents в продвинутой схеме охоты
description: Узнайте о событиях проверки подлинности или регистрации в таблице DeviceLogonEvents в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, logonevents, DeviceLogonEvents, authentication, logon, sign in
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
ms.openlocfilehash: 62e0179f4a8c7b45d0c9743d2f133f9a10fb4c24
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934061"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender



Таблица в продвинутой схеме охоты содержит сведения о логосах пользователей и других событиях проверки `DeviceLogonEvents` подлинности на [](advanced-hunting-overview.md) устройствах. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!TIP]
> Подробные сведения о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в центре безопасности.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `ActionType` | string |Тип действий, которые вызвали событие |
| `LogonType` | Строка | Тип сеанса логотипа, в частности:<br><br> - **Interactive** — пользователь физически взаимодействует с машиной с помощью локальной клавиатуры и экрана<br><br> - Логотипы удаленного интерактивного **(RDP)** — пользователь взаимодействует с машиной удаленно с помощью удаленного рабочего стола, служб терминалов, удаленной помощи или других клиентов RDP.<br><br> - **Network** - Сеанс, инициированный при доступе к машине с помощью PsExec или при доступе к общим ресурсам на машине, таким как принтеры и общие папки.<br><br> - **Batch** — Сеанс, инициированный запланированными задачами<br><br> - **Служба** — сеанс, инициированный службами при запуске<br> |
| `AccountDomain` | Строка | Домен учетной записи |
| `AccountName` | Строка | Имя пользователя учетной записи |
| `AccountSid` | Строка | Идентификатор безопасности (SID) учетной записи |
| `Protocol` | Строка | Протокол, используемый во время связи |
| `FailureReason` | Строка | Сведения, объясняющие причины сбой записанного действия |
| `IsLocalAdmin` | boolean | Индикатор Boolean о том, является ли пользователь локальным администратором на компьютере |
| `LogonId` | Строка | Идентификатор для сеанса логотипа. Этот идентификатор уникален на одной машине только между перезапусками |
| `RemoteDeviceName` | Строка | Имя машины, которая выполняла удаленную операцию на пораженной машине. В зависимости от сообщаемого события это имя может быть полностью квалифицированным доменным именем (FQDN), именем NetBIOS или хост-именем без сведений о домене. |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `RemoteIPType` | Строка | Тип IP-адресов, например public, Private, Reserved, Loopback, Teredo, FourToSixMapping и Broadcast |
| `RemotePort` | int | TCP-порт на удаленном устройстве, подключенного к |
| `InitiatingProcessAccountDomain` | Строка | Домен учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountName` | Строка | Имя пользователя учетной записи, которая запустила процесс, ответственный за событие |
| `InitiatingProcessAccountSid` | Строка | Идентификатор безопасности (SID) учетной записи, которая управляла процессом, ответственным за событие |
| `InitiatingProcessAccountUpn` | Строка | Основное имя пользователя (UPN) учетной записи, которая управляла процессом, ответственным за событие |
| ` InitiatingProcessAccountObjectId` | Строка | ID объекта Azure AD учетной записи пользователя, которая запустила процесс, ответственный за событие |
| `InitiatingProcessIntegrityLevel` | Строка | Уровень целостности процесса, который инициировал событие. Windows назначает уровни целостности процессам, основанным на определенных характеристиках, например, если они были запущены из скачивания в Интернете. Эти уровни целостности влияют на разрешения на ресурсы |
| `InitiatingProcessTokenElevation` | Строка | Тип маркера, указывающий на наличие или отсутствие высоты привилегий управления пользовательским доступом (UAC), применяемой к процессу, инициировал событие. |
| `InitiatingProcessSHA1` | Строка | SHA-1 процесса (файла изображений), который инициировал событие |
| `InitiatingProcessSHA256` | Строка | SHA-256 процесса (файла изображений), который инициировал событие. Это поле обычно не заполнено— используйте столбец SHA1 при наличии |
| `InitiatingProcessMD5` | Строка | AD5 hash of the process (image file), that initiated the event |
| `InitiatingProcessFileName` | Строка | Имя процесса, который инициировал событие |
| `InitiatingProcessFileSize` | long | Размер файла, который запустил процесс, ответственный за событие |
| `InitiatingProcessVersionInfoCompanyName` | Строка | Название компании из сведений о версии процесса (файла изображений), ответственного за событие |
| `InitiatingProcessVersionInfoProductName` | Строка | Имя продукта из сведений о версии процесса (файл изображений), ответственных за событие |
| `InitiatingProcessVersionInfoProductVersion` | Строка | Версия продукта из сведений о версии процесса (файла изображений), ответственного за событие |
| `InitiatingProcessVersionInfoInternalFileName` | Строка | Имя внутреннего файла из сведений о версии процесса (файла изображений), ответственного за событие |
| `InitiatingProcessVersionInfoOriginalFileName` | Строка | Исходное имя файла из версии данных процесса (файла изображений), ответственного за событие |
| `InitiatingProcessVersionInfoFileDescription` | Строка | Описание из сведений о версии процесса (файла изображений), ответственного за событие |
| `InitiatingProcessId` | int | Процесс ID (PID) процесса, который инициировал событие |
| `InitiatingProcessCommandLine` | Строка | Командная строка, используемая для запуска процесса, инициированного событием |
| `InitiatingProcessCreationTime` | datetime | Дата и время начала процесса запуска события |
| `InitiatingProcessFolderPath` | Строка | Папка, содержащая процесс (файл изображений), который инициировал событие |
| `InitiatingProcessParentId` | int | Process ID (PID) родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentFileName` | Строка | Имя родительского процесса, который породил процесс, ответственный за событие |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время запуска родительского процесса, ответственного за событие |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp. |
| `AppGuardContainerId` | Строка | Идентификатор виртуализированного контейнера, используемого службой Application Guard для изоляции активности браузера |
| `AdditionalFields` | Строка | Дополнительные сведения о событии в формате массива JSON |

## <a name="related-topics"></a>Похожие темы
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
