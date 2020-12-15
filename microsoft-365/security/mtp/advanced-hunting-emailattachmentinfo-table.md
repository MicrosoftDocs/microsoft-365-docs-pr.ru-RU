---
title: Таблица EmailAttachmentInfo в схеме расширенного поиска
description: Сведения о вложениях электронной почты в таблице EmailAttachmentInfo схемы расширенного поиска
keywords: расширенный поиск, охота на угрозы, поиск киберугроз, защита от угроз (Майкрософт), Microsoft 365, mtp, m365, поиск, запрос, телеметрия, справочник по схеме, kusto, таблица, столбец, тип данных, описание, EmailAttachmentInfo, код сетевого сообщения, отправитель, получатель, ид вложения, имя вложения, решение о вредоносных программах
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
ms.openlocfilehash: 6d88303b34f78abc857e9aec749bf2f58090f43a
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667653"
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
| `AttachmentId` | string | Уникальный идентификатор вложения электронной почты |
| `NetworkMessageId` | string | Уникальный идентификатор электронной почты, созданный Microsoft 365 |
| `SenderFromAddress` | string | Адрес электронной почты отправителя в заголовке "ОТ", который получатели электронной почты видят в своих почтовых клиентах |
| `RecipientEmailAddress` | string | Адрес электронной почты получателя или адрес электронной почты получателя после расширения списка рассылки |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FileType` | string | Тип расширения файла |
| `SHA256` | string | SHA-256 файла, к которому было применено записанное действие Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `MalwareFilterVerdict` | string | Решение модуля фильтрации электронной почты о том, содержит ли это сообщение вредоносную программу: "Вредоносное" или "Не вредоносное" |
| `MalwareDetectionMethod` | string | Метод, используемый для обнаружения вредоносных программ в электронной почте: антивредоносный механизм, репутация файла, безопасные вложения |
| `SenderDisplayName` | Строка | Имя отправитель, отображаемого в адресной книге, обычно сочетание имени или имени, отчего инициал и фамилия или фамилия |
| `SenderObjectId` | Строка | Уникальный идентификатор учетной записи отправитель в Azure AD |
| `ThreatTypes` | Строка | Решение из стека фильтрации электронной почты о том, содержит ли электронная почта вредоносные программы, фишинг или другие угрозы |
| `ThreatNames` | Строка | Имя обнаружения вредоносных программ или других найденных угроз |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
