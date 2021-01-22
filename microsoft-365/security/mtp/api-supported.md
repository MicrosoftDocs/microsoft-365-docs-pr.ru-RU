---
title: Поддерживаемые API Microsoft 365 Defender
description: Поддерживаемые API Microsoft 365 Defender
keywords: MTP, API, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ee03e5a255a88c084403842e7bf0319c06c0517b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926202"
---
# <a name="supported-microsoft-365-defender-apis"></a>Поддерживаемые API Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="list-of-available-apis"></a>Список доступных API

Статья | Описание
-|-
[Программный интерфейс расширенной охоты](api-advanced-hunting.md) | Выполнение запросов "Расширенный поиск".
[Программные интерфейсы, относящиеся к инцидентам](api-incident.md) | Список и обновление инцидентов, а также другие практические задачи.

### <a name="endpoint-uris"></a>IS конечных точек

Базовый URI для обоих основных API: https://api.security.microsoft.com . Для улучшения производительности используйте сервер, ближе к географическому местонахождению:

- США: api-us.security.microsoft.com
- Европа: api-eu.security.microsoft.com
- Соединенное Королевство: api-uk.security.microsoft.com

Маркеры можно получить с помощью https://api.security.microsoft.com доступа.

Все API на пути используют протокол `/api` [OData,](https://docs.microsoft.com/odata/overview) например https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Статьи по теме

- [Обзор API Microsoft 365 Defender](api-overview.md)
- [Доступ к API Защиты от угроз (Майкрософт)](api-access.md)
- [Узнайте об ограничениях API и лицензировании](api-terms.md)
- [Коды ошибок](api-error-codes.md)
