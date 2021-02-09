---
title: Таблица DeviceLogonEvents в схеме advanced hunting
description: Узнайте о событиях проверки подлинности или входе в таблицу DeviceLogonEvents схемы advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, logonevents, DeviceLogonEvents, authentication, logon, sign in
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 60455c0a66548654da52544e3d7ece84aecb9cf3
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145443"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender



Таблица в схеме advanced hunting содержит сведения о пользователях и других событиях проверки подлинности `DeviceLogonEvents` на устройствах. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!TIP]
> Для получения подробных сведений о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в Центре безопасности. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `ActionType` | string |Тип действия, которое вызвало событие |
| `AccountDomain` | string | Домен учетной записи |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `Protocol` | string | Протокол, используемый во время связи |
| `FailureReason` | string | Сведения о причине сбой записанного действия |
| `LogonType` | string | Тип сеанса для работы с логотипом, в частности:<br><br> - **Интерактивный** — пользователь физически взаимодействует с компьютером с помощью локальной клавиатуры и экрана<br><br> - **Удаленные интерактивные учетные** записи для работы с пользователями ( RDP) — пользователь удаленно взаимодействует с компьютером с помощью удаленного рабочего стола, служб терминалов, удаленной помощи или других клиентов RDP.<br><br> - **Сеть** — сеанс, инициированный при доступе к компьютеру с помощью PsExec или при доступе к общим ресурсам на компьютере, таким как принтеры и общие папки<br><br> - **Batch —** сеанс, инициированный запланированными задачами<br><br> - **Служба** — сеанс, инициированный службами при их запуске<br> |
| `LogonId` | string | Идентификатор сеанса logon. Этот идентификатор уникален на одном компьютере только между перезапусками |
| `RemoteDeviceName` | string | Имя компьютера, который выполнил удаленную операцию на затронутом компьютере. В зависимости от сообщаемого события это имя может быть полностью доменным именем, netBIOS-именем или именем хоста без сведений о домене. |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `RemoteIPType` | string | Тип IP-адреса, например Public, Private, Reserved, Loopback, Teredo, FourToSixMapping и Broadcast |
| `RemotePort` | int | TCP-порт на удаленном устройстве, к |
| `AdditionalFields` | string | Дополнительные сведения о событии в формате массива JSON |
| `InitiatingProcessFileSize` | long | Размер файла, который запустил процесс, отвечающий за событие |
| `InitiatingProcessAccountDomain` | string | Домен учетной записи, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessAccountName` | string | Имя пользователя учетной записи, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessAccountSid` | string | Идентификатор безопасности (SID) учетной записи, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessAccountUpn` | string | Имя пользователя-пользователя (UPN) учетной записи, которая запустила процесс, отвечающий за событие |
| ` InitiatingProcessAccountObjectId` | string | ИД объекта Azure AD учетной записи пользователя, которая запустила процесс, отвечающий за событие |
| `InitiatingProcessIntegrityLevel` | string | Уровень целостности процесса, который инициировал событие. Windows назначает уровни целостности процессам на основе определенных характеристик, например, если они были запущены из скачивания из Интернета. Эти уровни целостности влияют на разрешения для ресурсов |
| `InitiatingProcessTokenElevation` | string | Тип маркера, указывающий на наличие или отсутствие повышения привилегий контроля доступа пользователей (UAC), примененного к процессу, который инициировал событие |
| `InitiatingProcessSHA1` | string | SHA-1 процесса (файла изображения), который инициировал событие |
| `InitiatingProcessSHA256` | string | SHA-256 процесса (файла изображения), который инициировал событие. Это поле обычно не заполняется — используйте столбец SHA1, если он доступен |
| `InitiatingProcessMD5` | string | AD5 hash of the process (image file) that initiated the event |
| `InitiatingProcessFileName` | string | Имя процесса, который инициировал событие |
| `InitiatingProcessId` | int | ИД процесса, который инициировал событие |
| `InitiatingProcessCommandLine` | string | Командная строка, используемая для запуска процесса, который инициировал событие |
| `InitiatingProcessCreationTime` | datetime | Дата и время запуска процесса, который инициировал событие |
| `InitiatingProcessFolderPath` | string | Папка, содержащая процесс (файл изображения), который инициировал событие |
| `InitiatingProcessParentId` | int | ИД (PID) родительского процесса, который ил процесса, ответственного за событие |
| `InitiatingProcessParentFileName` | string | Имя родительского процесса, который ил процесса, ответственного за событие |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время начала родительского процесса, ответственного за событие |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец необходимо использовать вместе со столбцами DeviceName и Timestamp. |
| `AppGuardContainerId` | string | Идентификатор виртуализированного контейнера, используемого Application Guard для изоляции активности браузера |
| `IsLocalAdmin` | boolean | Boolean indicator of whether the user is a local administrator on the machine |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
