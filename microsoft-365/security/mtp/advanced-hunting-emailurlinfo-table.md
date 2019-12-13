---
title: Таблица EmailUrlInfo в схеме расширенного поиска
description: Информация об URL или ссылках приведена в таблице EmailUrlInfo схемы расширенного поиска.
keywords: расширенный поиск, поиск угроз, поиск киберугроз, поиск, запрос, телеметрия, справочник схемы, kusto, таблица, столбец, тип данных, описание, EmailUrlInfo, идентификатор сетевого сообщения, url, ссылка
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 10cf82667fd97eebe66c376e0539db000f20b1c2
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911553"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**Область применения:**
- Защита от угроз (Майкрософт)

[!include[Prerelease information](prerelease.md)]

`EmailUrlInfo`Таблица в схеме [расширенного поиска](advanced-hunting-overview.md) содержит информацию об адресах URL для сообщений электронной почты или вложений, обрабатываемых Office 365 ATP. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `EventTime` | datetime | Дата и время записи события |
| `UrlId` | string | Уникальный идентификатор URL в теме, основном тексте или вложении сообщения электронной почты |
| `NetworkMessageId` | string | Уникальный идентификатор сообщения электронной почты, сформированный в Office 365 |
| `Url` | string | Уникальный идентификатор URL в теме, основном тексте или вложении |

## <a name="related-topics"></a>См. также
- [Профилактический поиск угроз](advanced-hunting-overview.md)
- [Сведения о языке запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Общие сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)