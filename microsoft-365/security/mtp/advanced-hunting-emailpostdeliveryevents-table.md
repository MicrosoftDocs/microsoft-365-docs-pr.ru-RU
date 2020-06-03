---
title: Таблица емаилпостделиверевентс в схеме расширенного поискового окна
description: Сведения о действиях после доставки, выполняемых в сообщениях электронной почты Microsoft 365 в таблице Емаилпостделиверевентс расширенной схемы подхождения
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справочник по схемам, Кусто, таблица, столбец, тип данных, описание, Емаилпостделиверевентс, идентификатор сетевого сообщения, отправитель, получатель, идентификатор вложения, имя вложения, идентификатор сообщения, отправитель, фишинг вредоносности
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
ms.openlocfilehash: f4b34abdbfcbd6c3a2f142001a3d486485c86fcd
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515937"
---
# <a name="emailpostdeliveryevents"></a>емаилпостделиверевентс

**Область применения:**
- Защита от угроз (Майкрософт)

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`EmailPostDeliveryEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о действиях после доставки, выполняемых в сообщениях электронной почты, обработанных Microsoft 365. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Для получения дополнительных сведений об отдельных сообщениях электронной почты можно также использовать [`EmailEvents`](advanced-hunting-emailevents-table.md) таблицы, [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) и [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) . Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `EventId` | string | Уникальный идентификатор для события |
| `NetworkMessageId` | string | Уникальный идентификатор электронного сообщения, созданного Microsoft 365 |
| `InternetMessageId` | string | Общедоступный идентификатор сообщения электронной почты, устанавливаемый системой отправки электронной почты |
| `Action` | string | Действие, выполняемое с объектом |
| `ActionType` | string | Тип действия, вызвавшего событие: ручное исправление, фишинг ZAP, вредоносный ZAP |
| `ActionTrigger` | string | Указывает, было ли действие инициировано администратором (вручную или с помощью утверждения ожидающего автоматического действия) или с помощью какого-либо специального механизма, такого как ZAP или динамическая доставка. |
| `ActionResult` | string | Результат действия |
| `RecipientEmailAddress` | string | Адрес электронной почты получателя или адрес электронной почты получателя после расширения списка рассылки |
| `DeliveryLocation` | string | Место доставки сообщения: "Входящие" или другая папка, локальная или внешняя среда, "Спам", "Карантин", "Не выполнено", "Отброшенные" или "Удаленные" |

## <a name="supported-event-types"></a>Поддерживаемые типы событий
В этой таблице регистрируются события со следующими `ActionType` значениями:

- **Ручное исправление** — администратор вручную предпринимает действия над электронным сообщением после его доставки в почтовый ящик пользователя. Сюда входят действия, выполняемые вручную с помощью [проводника по угрозам](../office-365-security/threat-explorer.md) или утверждения [автоматизированных расследований и действий](mtp-autoir-actions.md), выполняемых в среде.
- **ФИШИНГ ZAP** — [Автоматическая очистка с нулевой ставкой (ZAP)](../office-365-security/zero-hour-auto-purge.md) выполнила действие по фишинговой почте после доставки.
- **Вредоносный ZAP** — автоматическая очистка с нулевой нагрузкой (ZAP) заняла бы какое-либо сообщение электронной почты, содержащее вредоносную программу после доставки.

## <a name="related-topics"></a>Статьи по теме
- [Заблаговременный поиск угроз](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)