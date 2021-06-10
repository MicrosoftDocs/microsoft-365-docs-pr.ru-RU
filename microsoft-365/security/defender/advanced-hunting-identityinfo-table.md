---
title: Таблица IdentityInfo в продвинутой схеме охоты
description: Сведения о учетной записи пользователя в таблице IdentityInfo в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, ссылка схемы, кусто, таблица, столбец, тип данных, описание, AccountInfo, IdentityInfo, учетная запись
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
ms.openlocfilehash: ce1a3d5153d324d008d2d46048838351eb7bc047
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935825"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица `IdentityInfo` в [продвинутой](advanced-hunting-overview.md) схеме охоты содержит сведения о учетных записях пользователей, полученных из различных служб, включая Azure Active Directory. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!NOTE]
>Эта таблица была переименована из `AccountInfo` . При переименовании все запросы, сохраненные на портале, автоматически обновляются. Проверьте запросы, сохраненные в другом месте.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure AD |
| `AccountUpn` | Строка | Основное имя пользователя (UPN) учетной записи |
| `OnPremSid` | Строка | Идентификатор локальной безопасности (SID) учетной записи |
| `CloudSid` | Строка | Идентификатор облачной безопасности учетной записи |
| `GivenName` | Строка | Имя или имя пользователя учетной записи |
| `Surname` | Строка | Фамилия, фамилия или фамилия пользователя учетной записи |
| `AccountDisplayName` | Строка | Имя пользователя учетной записи, отображаемого в адресной книге. Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии. |
| `Department` | Строка | Имя отдела, к которой принадлежит пользователь учетной записи |
| `JobTitle` | Строка | Название задания пользователя учетной записи |
| `AccountName` | Строка | Имя пользователя учетной записи |
| `AccountDomain` | Строка | Домен учетной записи |
| `EmailAddress` | Строка | SMTP-адрес учетной записи |
| `SipProxyAddress` | Строка | Протокол инициации сеанса голосовой связи по IP (VOIP) учетной записи |
| `City` | Строка | Город, в котором находится пользователь учетной записи |
| `Country` | Строка | Страна/регион, где находится пользователь учетной записи |
| `IsAccountEnabled` | boolean | Указывает, включена учетная запись или нет. |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
