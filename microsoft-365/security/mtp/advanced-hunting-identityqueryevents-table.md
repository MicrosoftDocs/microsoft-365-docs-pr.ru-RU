---
title: Таблица идентитикуеревентс в схеме расширенного поискового окна
description: Сведения о событиях запросов Active Directory в таблице Идентитикуеревентс расширенной схемы поиска
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Идентитикуеревентс, Azure AD, Active Directory, Azure ATP, удостоверения, запросы LDAP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: cf2038a15242139817eb073ec2a6408905824123
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649323"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

**Область применения:**
- Защита от угроз (Майкрософт)

`IdentityQueryEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о запросах, выполненных для объектов Active Directory, таких как пользователи, группы, устройства и домены. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действия, вызвавшего событие |
| `Application` | string | Приложение, которое выполнило записанное действие |
| `QueryType` | string | Тип запроса, например Куериграуп, Куерюсер или Енумератеусерс |
| `QueryTarget` | string | Имя пользователя, группы, устройства, домена или любого другого типа сущностей, запрашиваемых |
| `Query` | string | Строка, используемая для выполнения запроса |
| `Protocol` | string | Протокол, используемый при обмене данными |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | string | Домен учетной записи |
| `AccountUpn` | string | Имя участника-пользователя (UPN) учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure AD |
| `AccountDisplayName` | string | Имя пользователя учетной записи, отображаемое в адресной книге. Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия. |
| `DeviceName` | string | Полное доменное имя (FQDN) конечной точки |
| `IPAddress` | string | IP-адрес, назначенный конечной точке и используемый во время связанных сетевых коммуникаций |
| `DestinationDeviceName` | string | Имя устройства, на котором работает серверное приложение, которое обработало записанное действие |
| `DestinationIPAddress` | string | IP-адрес устройства, на котором запущено серверное приложение, которое обработало записанное действие |
| `TargetDeviceName` | string | Полное доменное имя (FQDN) устройства, к которому было применено записанное действие |
| `TargetAccountUpn` | string | Имя участника-пользователя (UPN) учетной записи, к которой было применено записанное действие |
| `TargetAccountDisplayName` | string | Отображаемое имя учетной записи, к которой было применено записанное действие |
| `Location` | string | Город, страна или другое географическое расположение, связанное с событием |
| `ReportId` | long | Уникальный идентификатор для события |
| `AdditionalFields` | string | Дополнительные сведения о сущности или событии |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Слежение за устройствами, сообщениями электронной почты, приложениями и удостоверениями](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
