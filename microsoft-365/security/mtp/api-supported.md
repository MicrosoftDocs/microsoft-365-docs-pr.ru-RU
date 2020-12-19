---
title: Поддерживаемые API Microsoft 365 Defender
description: Поддерживаемые API Microsoft 365 Defender
keywords: MTP, API, api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719326"
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
