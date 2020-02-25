---
title: Таблица EmailUrlInfo в схеме расширенного поиска
description: Информация об URL или ссылках приведена в таблице EmailUrlInfo схемы расширенного поиска.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Емаилурлинфо, идентификатор сетевого сообщения, URL-адрес, ссылка
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
ms.openlocfilehash: 7f5912306700efa0db704fe8d0c0db006105fda6
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234768"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**Область применения:**
- Защита от угроз (Майкрософт)



`EmailUrlInfo`Таблица в схеме [расширенного поиска](advanced-hunting-overview.md) содержит информацию об адресах URL для сообщений электронной почты или вложений, обрабатываемых Office 365 ATP. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
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
