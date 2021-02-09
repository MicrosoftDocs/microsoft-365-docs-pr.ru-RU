---
title: Таблица EmailAttachmentInfo в схеме расширенного поиска
description: Сведения о вложениях электронной почты в таблице EmailAttachmentInfo схемы расширенного поиска
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailAttachmentInfo, network message id, sender, recipient, attachment id, attachment name, malware verdict
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b810d7b15ef47a33a0675086219d2193cea00f2e
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145023"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender



Таблица в схеме advanced hunting содержит сведения о вложениях в сообщениях электронной почты, обрабатываемых `EmailAttachmentInfo` Microsoft Defender для Office 365. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `NetworkMessageId` | string | Уникальный идентификатор электронной почты, созданный Microsoft 365 |
| `SenderFromAddress` | string | Адрес электронной почты отправителя в заголовке "ОТ", который получатели электронной почты видят в своих почтовых клиентах |
| `SenderDisplayName` | string | Имя отправитель, отображаемого в адресной книге, обычно сочетание имени или имени, отчего инициал и фамилия или фамилия |
| `SenderObjectId` | string | Уникальный идентификатор учетной записи отправитель в Azure AD |
| `RecipientEmailAddress` | string | Адрес электронной почты получателя или адрес электронной почты получателя после расширения списка рассылки |
| `RecipientObjectId` | string | Уникальный идентификатор получателя электронной почты в Azure AD |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FileType` | string | Тип расширения файла |
| `SHA256` | string | SHA-256 файла, к которому было применено записанное действие Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `MalwareFilterVerdict` | string | Решение модуля фильтрации электронной почты о том, содержит ли это сообщение вредоносную программу: "Вредоносное" или "Не вредоносное" |
| `MalwareDetectionMethod` | string | Метод, используемый для обнаружения вредоносных программ в электронной почте: антивредоносный механизм, репутация файла, безопасные вложения |
| `ThreatTypes` | string | Решение из стека фильтрации электронной почты о том, содержит ли электронная почта вредоносные программы, фишинг или другие угрозы |
| `ThreatNames` | string | Имя обнаружения вредоносных программ или других найденных угроз |
| `DetectionMethods` | string | Методы обнаружения вредоносных программ, фишинга и других угроз, обнаруженных в сообщении электронной почты |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец необходимо использовать в сочетании со столбцами DeviceName и Timestamp. |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
