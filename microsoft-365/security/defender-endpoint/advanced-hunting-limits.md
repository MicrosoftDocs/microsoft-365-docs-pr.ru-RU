---
title: Расширенные ограничения на охоту в ATP Защитника Майкрософт
description: Разграничить различные ограничения службы, которые будут поддерживать отзывчивость передовой службы охоты
keywords: продвинутая охота, охота на угрозы, поиск киберугроз, mdatp, microsoft defender atp, wdatp, поиск, запрос, телеметрия, схема, кусто, ограничение ЦП, ограничение запросов, ресурсы, максимальные результаты
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
ms.technology: mde
ms.openlocfilehash: 8a9279d1dd2a6465553b576609bb81cdf4e03fa0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499529"
---
# <a name="advanced-hunting-service-limits"></a>Расширенные ограничения службы охоты

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Чтобы служба выполняла и реагировала, расширенный режим охоты устанавливает различные ограничения для запросов, выполняемых вручную и по пользовательским [правилам обнаружения.](custom-detection-rules.md) Чтобы понять эти ограничения, обратитесь к следующей таблице.

| Ограничение | Size | Цикл обновления | Описание |
|--|--|--|--|
| Диапазон данных | 30 дней | Каждый запрос | Каждый запрос может искать данные за последние 30 дней. |
| Набор результатов | 10 000 строк | Каждый запрос | Каждый запрос может возвращать до 10 000 записей. |
| Timeout | 10 минут | Каждый запрос | Каждый запрос может работать до 10 минут. Если он не завершится в течение 10 минут, служба отображает ошибку.
| Ресурсы ЦП | В зависимости от размера клиента | - В час, а затем каждые 15 минут<br>- Ежедневно в 12 полночь | Служба обеспечивает ежедневное и 15-минутное ограничение отдельно. Для каждого ограничения портал [отображает](advanced-hunting-errors.md) ошибку всякий раз, когда выполняется запрос, и клиент потребляет более 10% выделенных ресурсов. Запросы блокируют, если клиент достиг 100% до следующего ежедневного или 15-минутного цикла. |

>[!NOTE] 
>Отдельный набор ограничений применяется к расширенным запросам на охоту, выполняемым через API. [Ознакомьтесь с расширенными API охоты](run-advanced-query-api.md)

Клиенты, которые регулярно запускают [](advanced-hunting-best-practices.md) несколько запросов, должны отслеживать потребление и применять оптимальные методы оптимизации, чтобы свести к минимуму нарушения в результате превышения этих ограничений.

## <a name="related-topics"></a>Статьи по теме

- [Передовые методы охоты](advanced-hunting-best-practices.md)
- [Обработка ошибок, совершенных в области охоты](advanced-hunting-errors.md)
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Правила настраиваемой диагностики](custom-detection-rules.md)
