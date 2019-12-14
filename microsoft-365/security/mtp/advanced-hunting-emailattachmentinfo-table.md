---
title: Таблица EmailAttachmentInfo в схеме расширенного поиска
description: Сведения о вложениях электронной почты в таблице EmailAttachmentInfo схемы расширенного поиска
keywords: расширенный поиск, поиск угроз, поиск киберугроз, поиск, запрос, телеметрия, ссылка на схему, Kusto, таблица, столбец, тип данных, описание, EmailAttachmentInfo, идентификатор сетевого сообщения, отправитель, получатель, идентификатор вложения, имя вложения, решение о наличии вредоносной программы
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
ms.openlocfilehash: 9f6a4aa68826133bee0437116b2fbf3fde4e7e00
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911538"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

**Область применения:**
- Защита от угроз (Майкрософт)

[!include[Prerelease information](prerelease.md)]

Таблица `EmailAttachmentInfo` в схеме [расширенного поиска](advanced-hunting-overview.md) содержит информацию о вложениях в сообщения электронной почты, обрабатываемых Office 365 ATP. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `EventTime` | datetime | Дата и время записи события |
| `AttachmentId` | string | Уникальный идентификатор вложения электронной почты |
| `NetworkMessageId` | string | Уникальный идентификатор сообщения электронной почты, сформированный в Office 365 |
| `SenderFromAddress` | string | Адрес электронной почты отправителя в заголовке "ОТ", который получатели электронной почты видят в своих почтовых клиентах |
| `RecipientEmailAddress` | string | Адрес электронной почты получателя или адрес электронной почты получателя после расширения списка рассылки |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FileType` | string | Тип расширения файла |
| `SHA256` | string | SHA-256 файла, к которому было применено записанное действие Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `MalwareFilterVerdict` | string | Решение модуля фильтрации электронной почты о том, содержит ли это сообщение вредоносную программу: "Вредоносное" или "Не вредоносное" |
| `MalwareDetectionMethod` | string | Метод, используемый для обнаружения вредоносных программ в сообщении электронной почты: модуль защиты от вредоносных программ, репутация файлов, безопасные вложения ATP |

## <a name="related-topics"></a>См. также
- [Заблаговременный поиск угроз](advanced-hunting-overview.md)
- [Сведения о языке запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Общие сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)