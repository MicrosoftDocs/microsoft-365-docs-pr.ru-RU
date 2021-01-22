---
title: Таблица IdentityDirectoryEvents в схеме advanced hunting
description: Узнайте о событиях контроллера домена и Active Directory в таблице IdentityDirectoryEvents схемы advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityDirectoryEvents, domain controller, Active Directory, Azure ATP, identities
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
ms.openlocfilehash: 95090b0f4abe0b0f0552c81495936f4f2261cf8e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929938"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица в схеме advanced hunting содержит события, связанные с контроллером локального домена под управлением `IdentityDirectoryEvents` Active Directory [](advanced-hunting-overview.md) (AD). В этой таблице фиксироваться различные события, связанные с удостоверениями, такие как изменение паролей, истечение срока действия пароля и изменение имени пользователя-пользователя. Он также захватывает системные события на контроллере домена, такие как планирование задач и действия PowerShell. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!TIP]
> Для получения подробных сведений о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в Центре безопасности. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действия, которое вызвало событие. Подробные сведения см. в справке [по схеме портала](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | string | Приложение, которое выполнило записанную действие |
| `TargetAccountUpn` | string | Имя пользователя-пользователя (UPN) учетной записи, к которую было применено записанное действие |
| `TargetAccountDisplayName` | string | Отображаемого имени учетной записи, к которую было применено записанное действие |
| `TargetDeviceName` | string | Полное доменное имя (FQDN) устройства, к которого было применено записанное действие |
| `DestinationDeviceName` | string | Имя устройства, на которое запущено серверное приложение, обрабатывающее записанное действие |
| `DestinationIPAddress` | string | IP-адрес устройства, на которое запущено серверное приложение, обрабатывающее записанное действие |
| `DestinationPort` | string | Порт назначения действия |
| `Protocol` | string | Протокол, используемый во время связи |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | string | Домен учетной записи |
| `AccountUpn` | string | Имя пользователя-пользователя (UPN) учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure Active Directory |
| `AccountDisplayName` | string | Имя пользователя учетной записи, отображаемой в адресной книге. Обычно сочетание заданного или имени, инициации по середине и фамилии или фамилии. |
| `DeviceName` | string | Полное доменное имя устройства |
| `IPAddress` | string | IP-адрес, присвоенный устройству во время связи |
| `Port` | string | TCP-порт, используемый во время связи |
| `Location` | string | Город, страна или другое географическое расположение, связанное с событием |
| `ISP` | string | Поставщик услуг Интернета, связанный с IP-адресом |
| `ReportId` | long | Уникальный идентификатор события |
| `AdditionalFields` | string | Дополнительные сведения об объекте или событии |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
