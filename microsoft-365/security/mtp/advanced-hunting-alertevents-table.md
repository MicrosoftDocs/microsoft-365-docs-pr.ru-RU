---
title: Таблица AlertEvents в схеме расширенной охоты
description: Сведения о событиях создания оповещений в таблице AlertEvents схемы расширенной охоты
keywords: расширенная охота, охота на угрозы, охота на киберугрозы, поиск, запрос, телеметрия, справочник схемы, kusto, таблица, столбец, тип данных, описание, события оповещений, оповещение, серьезность, категория
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
ms.openlocfilehash: ee14dcc1c2ae0a2bc6fa3c094d757441515f00de
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807018"
---
# <a name="alertevents"></a>AlertEvents

**Область применения:**
- Защита от угроз (Майкрософт)

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

В таблице `AlertEvents` схемы [расширенной охоты](advanced-hunting-overview.md) содержится информация об оповещениях ATP в Microsoft Defender. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенной охоты см. в [справочнике по расширенной охоте](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `AlertId` | string | Уникальный идентификатор оповещения |
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `Severity` | string | Указывает возможное воздействие (высокое, среднее или низкое) индикатора угрозы или нарушения, определенного оповещением |
| `Category` | string | Тип индикатора угрозы или нарушения, определенного оповещением |
| `Title` | string | Название оповещения |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `RemoteUrl` | string | URL-адрес или полное доменное имя, к которому выполнено подключение |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец должен использоваться в сочетании со столбцами DeviceName и timestamp |
| `Table` | string | Таблица, содержащая сведения о событии |

## <a name="related-topics"></a>См. также
- [Профилактическая охота на угрозы](advanced-hunting-overview.md)
- [Сведения о языке запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на угрозы в электронной почте и устройствах](advanced-hunting-query-emails-devices.md)
- [Общие сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
