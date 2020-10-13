---
title: Таблица EmailAttachmentInfo в схеме расширенного поиска
description: Сведения о вложениях электронной почты в таблице EmailAttachmentInfo схемы расширенного поиска
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Емаилаттачментинфо, идентификатор сетевого сообщения, отправитель, имя получателя, идентификатор вложения, имя вложения и вредоносная вредоносности
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: dcacc31f8ea2546cbf90e45a4323a60670a98458
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429843"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)



Таблица `EmailAttachmentInfo` в схеме [расширенного поиска](advanced-hunting-overview.md) содержит информацию о вложениях в сообщения электронной почты, обрабатываемых Office 365 ATP. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `AttachmentId` | string | Уникальный идентификатор вложения электронной почты |
| `NetworkMessageId` | string | Уникальный идентификатор электронного сообщения, созданного Microsoft 365 |
| `SenderFromAddress` | string | Адрес электронной почты отправителя в заголовке "ОТ", который получатели электронной почты видят в своих почтовых клиентах |
| `RecipientEmailAddress` | string | Адрес электронной почты получателя или адрес электронной почты получателя после расширения списка рассылки |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FileType` | string | Тип расширения файла |
| `SHA256` | string | SHA-256 файла, к которому было применено записанное действие Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `MalwareFilterVerdict` | string | Решение модуля фильтрации электронной почты о том, содержит ли это сообщение вредоносную программу: "Вредоносное" или "Не вредоносное" |
| `MalwareDetectionMethod` | string | Метод, используемый для обнаружения вредоносных программ в сообщении электронной почты: модуль защиты от вредоносных программ, репутация файлов, безопасные вложения ATP |

## <a name="related-topics"></a>См. также
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Сведения о языке запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Общие сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
