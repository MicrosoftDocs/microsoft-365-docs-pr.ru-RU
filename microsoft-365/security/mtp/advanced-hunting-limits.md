---
title: Квоты advanced hunting и параметры использования в Microsoft 365 Defender
description: Различные квоты и параметры использования (ограничения служб), которые отвечают службе advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results, quota, parameters, allocation
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
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929794"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Квоты и параметры использования для расширенных охот

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Для поддержания быстрой работы службы и реагирования расширенный поиск задает различные квоты и параметры использования (также известные как "ограничения службы"). Эти квоты и параметры применяются к запросам, которые запускают вручную и [настраиваемые правила обнаружения.](custom-detection-rules.md) Клиенты, регулярно запуская несколько [](advanced-hunting-best-practices.md) запросов, должны отслеживать потребление и применять лучшие методики оптимизации, чтобы свести к минимуму нарушения.

Чтобы понять существующие квоты и параметры использования, обратитесь к следующей таблице.

| Квота или параметр | Size | Цикл обновления | Описание |
|--|--|--|--|
| Диапазон данных | 30 дней | Каждый запрос | Каждый запрос может искать данные за последние 30 дней. |
| Набор результатов | 10 000 строк | Каждый запрос | Каждый запрос может возвращать до 10 000 записей. |
| Timeout | 10 минут | Каждый запрос | Каждый запрос может работать до 10 минут. Если оно не завершится в течение 10 минут, служба отобразит ошибку.
| Ресурсы ЦП | В зависимости от размера клиента | - В час, а затем каждые 15 минут<br>- Ежедневно в 12 полночь | Служба принудительно применяет суточную и 15-минутную квоты отдельно. Для каждой квоты портал отображает ошибку при каждом запуске запроса, когда клиент потребляет более 10 % выделенных ресурсов. [](advanced-hunting-errors.md) Запросы блокируются, если клиент достиг 100 % до следующего ежедневного или 15-минутного цикла. |

>[!NOTE] 
>Отдельный набор квот и параметров применяется к запросам на расширенный поиск, выполняемый с помощью API. [Ознакомьтесь с API расширенных охот](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>Статьи по теме

- [Расширенные методы охоты](advanced-hunting-best-practices.md)
- [Обработка ошибок расширенных поисков](advanced-hunting-errors.md)
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Обзор настраиваемых обнаружений](custom-detections-overview.md)