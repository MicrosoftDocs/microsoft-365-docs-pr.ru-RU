---
title: Таблица IdentityInfo в схеме advanced hunting
description: Сведения об учетной записи пользователя в таблице IdentityInfo схемы advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AccountInfo, IdentityInfo, account
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
ms.openlocfilehash: 6604e6d48e277e840b87ddc461580bcb69dd1bc7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929914"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица в схеме advanced hunting содержит сведения об учетных записях пользователей, полученных из различных служб, включая `IdentityInfo` Azure Active [](advanced-hunting-overview.md) Directory. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!NOTE]
>Эта таблица была переименована `AccountInfo` из . Во время переименования все запросы, сохраненные на портале, автоматически обновляются. Проверьте запросы, сохраненные в другом месте.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure AD |
| `AccountUpn` | string | Имя пользователя-пользователя (UPN) учетной записи |
| `OnPremSid` | string | Идентификатор безопасности (SID) локальной учетной записи |
| `CloudSid` | string | Идентификатор облачной безопасности учетной записи |
| `GivenName` | string | Заданное имя или имя пользователя учетной записи |
| `Surname` | string | Фамилия, фамилия или фамилия пользователя учетной записи |
| `AccountDisplayName` | string | Имя пользователя учетной записи, отображаемой в адресной книге. Обычно сочетание заданного или имени, инициации по середине и фамилии или фамилии. |
| `Department` | string | Название отдела, в который входит пользователь учетной записи |
| `JobTitle` | string | Должность пользователя учетной записи |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | string | Домен учетной записи |
| `EmailAddress` | string | SMTP-адрес учетной записи |
| `SipProxyAddress` | string | SIP-адрес учетной записи по протоколу SIP |
| `City` | string | Город, где находится пользователь учетной записи |
| `Country` | string | Страна или регион, где находится пользователь учетной записи |
| `IsAccountEnabled` | boolean | Указывает, включена ли учетная запись |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
