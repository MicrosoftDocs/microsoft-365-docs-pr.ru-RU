---
title: Таблица EmailPostDeliveryEvents в продвинутой схеме охоты
description: Узнайте о действиях после доставки, принятых в электронной почте Microsoft 365 в таблице EmailPostDeliveryEvents в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailPostDeliveryEvents, network message id, sender, recipient, attachment id, attachment name, malware verdict, phishing verdict, attachment count, link count, url count
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
ms.openlocfilehash: 25f1a177571862e92c502b584bbd51801141069a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076701"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица в продвинутой схеме охоты содержит сведения о действиях после доставки, принятых в сообщениях электронной `EmailPostDeliveryEvents` почты, обработанных Корпорацией Майкрософт [](advanced-hunting-overview.md) 365. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!TIP]
> Подробные сведения о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в центре безопасности.

Чтобы получить дополнительные сведения об отдельных сообщениях электронной почты, вы также можете использовать [`EmailEvents`](advanced-hunting-emailevents-table.md) таблицы и [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) таблицы. Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `NetworkMessageId` | string | Уникальный идентификатор для электронной почты, созданный Корпорацией Майкрософт 365 |
| `InternetMessageId` | string | Общедоступный идентификатор сообщения электронной почты, устанавливаемый системой отправки электронной почты |
| `Action` | string | Действия, принятые в отношении объекта |
| `ActionType` | строка | Тип действий, которые вызвали событие: исправление вручную, Фишинг ZAP, ZAP вредоносных программ |
| `ActionTrigger` | строка | Указывает, было ли вызвано действие администратором (вручную или путем утверждения ожидающих автоматического действия) или каким-либо специальным механизмом, например ZAP или динамической доставкой. |
| `ActionResult` | строка | Результат действия |
| `RecipientEmailAddress` | string | Адрес электронной почты получателя или адрес электронной почты получателя после расширения списка рассылки |
| `DeliveryLocation` | string | Место доставки сообщения: "Входящие" или другая папка, локальная или внешняя среда, "Спам", "Карантин", "Не выполнено", "Отброшенные" или "Удаленные" |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp. |

## <a name="supported-event-types"></a>Поддерживаемые типы событий
В этой таблице запечатлены события со `ActionType` следующими значениями:

- **Исправление вручную** — администратор вручную принял меры по сообщению электронной почты после его доставки в почтовый ящик пользователя. Это включает действия, принятые вручную с помощью [обозревателя угроз](../defender-365-security/threat-explorer.md) или утверждения действий автоматического расследования [и реагирования (AIR).](m365d-autoir-actions.md)
- **Phish ZAP** — автоматическая очистка нулевого часа [(ZAP)](../defender-365-security/zero-hour-auto-purge.md) приняла меры по фишинговой электронной почте после доставки.
- **ZaP вредоносных** программ — автоматическая очистка нулевого часа (ZAP) приняла меры по сообщению электронной почты, обнаруженного с вредоносными программами после доставки.

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
