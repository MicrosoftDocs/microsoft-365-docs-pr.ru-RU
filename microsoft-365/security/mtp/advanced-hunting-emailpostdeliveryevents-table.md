---
title: Таблица EmailPostDeliveryEvents в схеме advanced hunting
description: Узнайте о действиях после доставки сообщений электронной почты Microsoft 365 в таблице EmailPostDeliveryEvents схемы advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailPostDeliveryEvents, network message id, sender, recipient, attachment id, attachment name, malware verdict, phishing verdict, attachment count, link count, url count
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 774676e15e9018b13674149b6a2e147a91000814
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145503"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица в схеме advanced hunting содержит сведения о действиях после доставки сообщений электронной почты, обрабатываемых `EmailPostDeliveryEvents` Microsoft 365. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!TIP]
> Для получения подробных сведений о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в Центре безопасности. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Чтобы получить дополнительные сведения об отдельных сообщениях электронной почты, можно также использовать таблицы [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) и [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) таблицы. Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `NetworkMessageId` | string | Уникальный идентификатор электронной почты, созданный Microsoft 365 |
| `InternetMessageId` | string | Общедоступный идентификатор сообщения электронной почты, устанавливаемый системой отправки электронной почты |
| `Action` | string | Действие, которое было предприняты с объектом |
| `ActionType` | string | Тип действия, которое вызвало событие: исправление вручную, фишинговая zap, zap вредоносных программ |
| `ActionTrigger` | string | Указывает, было ли действие инициировано администратором (вручную или путем утверждения ожидающих автоматических действий) или каким-либо специальным механизмом, например автоматической доставкой или автоматической доставкой. |
| `ActionResult` | string | Результат действия |
| `RecipientEmailAddress` | string | Адрес электронной почты получателя или адрес электронной почты получателя после расширения списка рассылки |
| `DeliveryLocation` | string | Место доставки сообщения: "Входящие" или другая папка, локальная или внешняя среда, "Спам", "Карантин", "Не выполнено", "Отброшенные" или "Удаленные" |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец необходимо использовать вместе со столбцами DeviceName и Timestamp. |

## <a name="supported-event-types"></a>Поддерживаемые типы событий
В этой таблице фиксировать события со `ActionType` следующими значениями:

- **Исправление вручную** — администратор вручную принял действие с сообщением электронной почты после его доставки в почтовый ящик пользователя. К ним относятся действия, вручную предпринятые с помощью [обозревателя угроз](../office-365-security/threat-explorer.md) или утверждения автоматизированных действий по расследованию и [реагированию на них (AIR).](mtp-autoir-actions.md)
- **Очистка фишинга** — автоматическая очистка [(ZAP)](../office-365-security/zero-hour-auto-purge.md) после доставки фишингового сообщения.
- **Автоматическая очистка** вредоносных программ —автоматическая очистка (ZAP) с сообщением электронной почты, содержащим вредоносную программу после доставки.

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
