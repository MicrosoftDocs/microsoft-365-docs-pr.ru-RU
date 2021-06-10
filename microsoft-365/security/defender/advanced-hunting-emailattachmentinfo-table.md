---
title: Таблица EmailAttachmentInfo в схеме расширенного поиска
description: Сведения о вложениях электронной почты в таблице EmailAttachmentInfo схемы расширенного поиска
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailAttachmentInfo, network message id, sender, recipient, attachment id, attachment name, malware verdict
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 961474fa62981364919ae3bf482a886eb9a5e821
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935501"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender



Таблица в продвинутой схеме охоты содержит сведения о вложениях в электронные письма, обработанные `EmailAttachmentInfo` Microsoft Defender для Office 365. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `NetworkMessageId` | string | Уникальный идентификатор для электронной почты, созданный Microsoft 365 |
| `SenderFromAddress` | string | Адрес электронной почты отправителя в заголовке "ОТ", который получатели электронной почты видят в своих почтовых клиентах |
| `SenderDisplayName` | string | Имя отправитель, отображаемого в адресной книге, как правило, сочетание заданного или имени, среднего начального и фамилии |
| `SenderObjectId` | Строка | Уникальный идентификатор учетной записи отправитель в Azure AD |
| `RecipientEmailAddress` | string | Адрес электронной почты получателя или адрес электронной почты получателя после расширения списка рассылки |
| `RecipientObjectId` | string | Уникальный идентификатор получателя электронной почты в Azure AD |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FileType` | string | Тип расширения файла |
| `SHA256` | string | SHA-256 файла, к которому было применено записанное действие Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `ThreatTypes` | string | Вердикт из стека фильтрации электронной почты о том, содержит ли электронная почта вредоносные программы, фишинг или другие угрозы |
| `ThreatNames` | Строка | Обнаружено имя обнаружения вредоносных программ или других найденных угроз |
| `DetectionMethods` | Строка | Методы обнаружения вредоносных программ, фишинга или других угроз, обнаруженных в электронной почте |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp. |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
