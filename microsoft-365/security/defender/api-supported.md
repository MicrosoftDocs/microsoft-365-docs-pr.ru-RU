---
title: Поддерживаемые API Microsoft 365 Defender
description: Поддерживаемые API Microsoft 365 Defender
keywords: Microsoft 365 Defender, API, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: acd8ec28fb1d78e3724cb0ca0ebee48133e7310f
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985088"
---
# <a name="supported-microsoft-365-defender-apis"></a>Поддерживаемые API Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

## <a name="list-of-available-apis"></a>Список доступных API

Статья | Описание
-|-
[API расширенной охоты](api-advanced-hunting.md) | Запустите расширенные запросы на охоту.
[Программные интерфейсы, относящиеся к инцидентам](api-incident.md) | Список и обновление инцидентов, а также другие практические задачи.
[Потоковый API](streaming-api.md) (Предварительный просмотр) | Отгрузка событий и оповещений в режиме реального времени в едином потоке данных.

### <a name="endpoint-uris"></a>URL-адреса конечной точки

Базовый URI для обоих основных API: https://api.security.microsoft.com . Чтобы улучшить производительность, используйте сервер ближе к геолокации:

- США: api-us.security.microsoft.com
- Европа: api-eu.security.microsoft.com
- Великобритания: api-uk.security.microsoft.com

Маркеры можно приобрести путем доступа https://api.security.microsoft.com к .

Все API на `/api` пути используют [протокол OData;](/odata/overview) https://api.security.microsoft.com/api/incidents например.

## <a name="related-articles"></a>Связанные статьи

- [Microsoft 365 Defender Обзор API](api-overview.md)
- [Доступ к Microsoft 365 Defender API](api-access.md)
- [API потоковой передачи](../defender-endpoint/raw-data-export.md)
- [Узнайте о ограничениях API и лицензировании](api-terms.md)
- [Понимание кодов ошибок](api-error-codes.md)
