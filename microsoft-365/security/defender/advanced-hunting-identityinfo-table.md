---
title: Таблица IdentityInfo в продвинутой схеме охоты
description: Сведения о учетной записи пользователя в таблице IdentityInfo в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, ссылка на схему, кусто, таблица, столбец, тип данных, описание, AccountInfo, IdentityInfo, учетная запись
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
ms.openlocfilehash: e3e5410c868336308b1ecb34ba4326bf2dc5796f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072774"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица в продвинутой схеме охоты содержит сведения о учетных записях пользователей, полученных из различных служб, в том числе `IdentityInfo` Azure Active [](advanced-hunting-overview.md) Directory. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!NOTE]
>Эта таблица была переименована из `AccountInfo` . При переименовании все запросы, сохраненные на портале, автоматически обновляются. Проверьте запросы, сохраненные в другом месте.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure AD |
| `AccountUpn` | строка | Основное имя пользователя (UPN) учетной записи |
| `OnPremSid` | строка | Идентификатор локальной безопасности (SID) учетной записи |
| `CloudSid` | строка | Идентификатор облачной безопасности учетной записи |
| `GivenName` | строка | Имя или имя пользователя учетной записи |
| `Surname` | строка | Фамилия, фамилия или фамилия пользователя учетной записи |
| `AccountDisplayName` | строка | Имя пользователя учетной записи, отображаемого в адресной книге. Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии. |
| `Department` | строка | Имя отдела, к которой принадлежит пользователь учетной записи |
| `JobTitle` | строка | Название задания пользователя учетной записи |
| `AccountName` | строка | Имя пользователя учетной записи |
| `AccountDomain` | строка | Домен учетной записи |
| `EmailAddress` | строка | SMTP-адрес учетной записи |
| `SipProxyAddress` | строка | Протокол инициации сеанса голосовой связи по IP (VOIP) учетной записи |
| `City` | строка | Город, в котором находится пользователь учетной записи |
| `Country` | строка | Страна/регион, где находится пользователь учетной записи |
| `IsAccountEnabled` | boolean | Указывает, включена учетная запись или нет. |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
