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
ms.openlocfilehash: 4d83b659a98c56cc59e88f9777aa73ca2e25b745
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911539"
---
# <a name="alertevents"></a>AlertEvents

**Область применения:**
- Защита от угроз (Майкрософт)

[!include[Prerelease information](prerelease.md)]

В таблице `AlertEvents` схемы [расширенной охоты](advanced-hunting-overview.md) содержится информация об оповещениях ATP в Microsoft Defender. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенной охоты см. в [справочнике по расширенной охоте](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `AlertId` | string | Уникальный идентификатор оповещения |
| `EventTime` | datetime | Дата и время записи события |
| `MachineId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `ComputerName` | string | Полное доменное имя компьютера |
| `Severity` | string | Указывает возможное воздействие (высокое, среднее или низкое) индикатора угрозы или нарушения, определенного оповещением |
| `Category` | string | Тип индикатора угрозы или нарушения, определенного оповещением |
| `Title` | string | Название оповещения |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `RemoteUrl` | string | URL-адрес или полное доменное имя, к которому выполнено подключение |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец требуется использовать в сочетании со столбцами ComputerName и EventTime |
| `Table` | string | Таблица, содержащая сведения о событии |

## <a name="related-topics"></a>См. также
- [Профилактическая охота на угрозы](advanced-hunting-overview.md)
- [Сведения о языке запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на угрозы в электронной почте и устройствах](advanced-hunting-query-emails-devices.md)
- [Общие сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
