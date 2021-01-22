---
title: Таблица IdentityQueryEvents в схеме advanced hunting
description: Узнайте о событиях запросов Active Directory в таблице IdentityQueryEvents схемы advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identities, LDAP queries
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
ms.openlocfilehash: 7016127a75bca48103f5325ce169faa3d7c31c85
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929818"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица в схеме advanced hunting содержит сведения о запросах, выполняемых к объектам Active Directory, таким как `IdentityQueryEvents` пользователи, группы, устройства и [](advanced-hunting-overview.md) домены. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!TIP]
> Для получения подробных сведений о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в Центре безопасности. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действия, которое вызвало событие. Подробные сведения см. в справке [по схеме портала](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | string | Приложение, которое выполнило записанную действие |
| `QueryType` | string | Тип запроса, например QueryGroup, QueryUser или EnumerateUsers |
| `QueryTarget` | string | Имя пользователя, группы, устройства, домена или любого другого типа объекта, для которого запрашивается |
| `Query` | string | Строка, используемая для выполнения запроса |
| `Protocol` | string | Протокол, используемый во время связи |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | string | Домен учетной записи |
| `AccountUpn` | string | Имя пользователя-пользователя (UPN) учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure AD |
| `AccountDisplayName` | string | Имя пользователя учетной записи, отображаемой в адресной книге. Обычно сочетание заданного или имени, инициации по середине и фамилии или фамилии. |
| `DeviceName` | string | Полное доменное имя конечной точки |
| `IPAddress` | string | IP-адрес, присвоенный конечной точке и используемый при связанных сетевых коммуникациях |
| `DestinationDeviceName` | string | Имя устройства, на которое запущено серверное приложение, обрабатывающее записанное действие |
| `DestinationIPAddress` | string | IP-адрес устройства, на которое запущено серверное приложение, обрабатывающее записанное действие |
| `TargetDeviceName` | string | Полное доменное имя (FQDN) устройства, к которого было применено записанное действие |
| `TargetAccountUpn` | string | Имя пользователя-пользователя (UPN) учетной записи, к которую было применено записанное действие |
| `TargetAccountDisplayName` | string | Отображаемого имени учетной записи, к которую было применено записанное действие |
| `Location` | string | Город, страна или другое географическое расположение, связанное с событием |
| `ReportId` | long | Уникальный идентификатор события |
| `AdditionalFields` | string | Дополнительные сведения об объекте или событии |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
