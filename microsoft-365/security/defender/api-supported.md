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
ms.openlocfilehash: f2c66dca326589807f5712c5548c177a0d08ade0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935729"
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
[Программный интерфейс расширенной охоты](api-advanced-hunting.md) | Запустите расширенные запросы на охоту.
[Программные интерфейсы, относящиеся к инцидентам](api-incident.md) | Список и обновление инцидентов, а также другие практические задачи.

### <a name="endpoint-uris"></a>URL-адреса конечной точки

Базовый URI для обоих основных API: https://api.security.microsoft.com . Чтобы улучшить производительность, используйте сервер ближе к геолокации:

- США: api-us.security.microsoft.com
- Европа: api-eu.security.microsoft.com
- Великобритания: api-uk.security.microsoft.com

Маркеры можно приобрести путем доступа https://api.security.microsoft.com к .

Все API на `/api` пути используют [протокол OData;](/odata/overview) https://api.security.microsoft.com/api/incidents например.

## <a name="related-articles"></a>Статьи по теме

- [Обзор API защитника Microsoft 365](api-overview.md)
- [Доступ к API защитника Microsoft 365](api-access.md)
- [Узнайте о ограничениях API и лицензировании](api-terms.md)
- [Понимание кодов ошибок](api-error-codes.md)