---
title: Таблица DeviceAlertEvents в продвинутой схеме охоты
description: Узнайте о событиях генерации оповещений в таблице DeviceAlertEvents продвинутой схемы охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, Microsoft Defender для конечной точки, поиск, запрос, телеметрия, ссылка схемы, kusto, таблица, столбец, тип данных, описание, DeviceAlertEvents, предупреждение, серьезность, категория
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: bb2350fed5fadee359695743989e02a3b3e44fb2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935345"
---
# <a name="devicealertevents"></a>DeviceAlertEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)



>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Таблица `DeviceAlertEvents` в [продвинутой схеме охоты](advanced-hunting-overview.md) содержит сведения о оповещениях в Центре безопасности Защитника Майкрософт. Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

Сведения о других таблицах в продвинутой схеме охоты см. в справке [о схеме охоты.](advanced-hunting-schema-reference.md)

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `AlertId` | string | Уникальный идентификатор оповещения |
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор устройства в службе |
| `DeviceName` | Строка | Полное доменное имя (FQDN) устройства |
| `Severity` | string | Указывает возможное воздействие (высокое, среднее или низкое) индикатора угрозы или нарушения, определенного оповещением |
| `Category` | string | Тип индикатора угрозы или нарушения, определенного оповещением |
| `Title` | string | Название оповещения |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `RemoteUrl` | string | URL-адрес или полное доменное имя, к которому выполнено подключение |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `AttackTechniques` | Строка | МЕТОДЫ ATT MITRE&CK, связанные с действиями, которые вызвали оповещение |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец должен использоваться совместно с `DeviceName` `Timestamp` столбцами и |
| `Table` | string | Таблица, содержащая сведения о событии |

## <a name="related-topics"></a>См. также
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
