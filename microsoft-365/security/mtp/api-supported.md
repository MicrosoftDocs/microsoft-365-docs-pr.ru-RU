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
ms.openlocfilehash: a162226793cc63a9e7e4d490c721a2c488ac64fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922178"
---
# <a name="supported-microsoft-365-defender-apis"></a>Поддерживаемые API Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно изданным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

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
- [Доступ к API microsoft Threat Protection](api-access.md)
- [Узнайте о ограничениях API и лицензировании](api-terms.md)
- [Понимание кодов ошибок](api-error-codes.md)