---
title: Таблица IdentityQueryEvents в продвинутой схеме охоты
description: Дополнительные данные о событиях запросов Active Directory в таблице IdentityQueryEvents в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, ссылка схемы, kusto, таблица, столбец, тип данных, описание, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identitys, LDAP-запросы
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
ms.openlocfilehash: f663a9dcc5bebd3a7fd124bbd0c0fece5dbb62e4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076357"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица в продвинутой схеме охоты содержит сведения о запросах, выполняемых в отношении объектов Active Directory, таких как `IdentityQueryEvents` пользователи, группы, устройства и [](advanced-hunting-overview.md) домены. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!TIP]
> Подробные сведения о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в центре безопасности.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действий, которые вызвали событие. Подробные [сведения см. в](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) справке по схеме на портале |
| `Application` | строка | Приложение, которое выполнило записанную акцию |
| `QueryType` | строка | Тип запроса, например QueryGroup, QueryUser или EnumerateUsers |
| `QueryTarget` | строка | Имя пользователя, группы, устройства, домена или любого другого типа объекта, запрашиваемого |
| `Query` | строка | Строка, используемая для выполнения запроса |
| `Protocol` | строка | Протокол, используемый во время связи |
| `AccountName` | строка | Имя пользователя учетной записи |
| `AccountDomain` | строка | Домен учетной записи |
| `AccountUpn` | строка | Основное имя пользователя (UPN) учетной записи |
| `AccountSid` | строка | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | строка | Уникальный идентификатор учетной записи в Azure AD |
| `AccountDisplayName` | строка | Имя пользователя учетной записи, отображаемого в адресной книге. Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии. |
| `DeviceName` | строка | Полное доменное имя (FQDN) конечной точки |
| `IPAddress` | строка | IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций |
| `Port` | строка | Порт TCP, используемый во время связи |
| `DestinationDeviceName` | строка | Имя устройства под управлением серверного приложения, обрабатываемого записанным действием |
| `DestinationIPAddress` | строка | IP-адрес устройства под управлением серверного приложения, обработав записанное действие |
| `DestinationPort` | строка | Порт назначения связанных сетевых коммуникаций |
| `TargetDeviceName` | строка | Полное доменное имя (FQDN) устройства, на которое было применено записанное действие |
| `TargetAccountUpn` | строка | Основное имя пользователя (UPN) учетной записи, к |
| `TargetAccountDisplayName` | строка | Отображение имени учетной записи, к которую было применено записанное действие |
| `Location` | строка | Город, страна или другое географическое расположение, связанное с событием |
| `ReportId` | long | Уникальный идентификатор события |
| `AdditionalFields` | строка | Дополнительные сведения об объекте или событии |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
