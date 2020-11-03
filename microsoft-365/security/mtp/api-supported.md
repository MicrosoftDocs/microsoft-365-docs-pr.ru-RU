---
title: Поддерживаемые API-интерфейсы защитника Microsoft 365
description: Поддерживаемые API-интерфейсы защитника Microsoft 365
keywords: MTP, API, API
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
ms.openlocfilehash: b7c0accf2d649d4ad6177260294922ee17783f2c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844964"
---
# <a name="supported-microsoft-365-defender-apis"></a>Поддерживаемые API-интерфейсы защитника Microsoft 365 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Защитник Microsoft 365

>[!IMPORTANT] 
>Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.


### <a name="end-point-uris"></a>URI конечных точек:

- Базовый URI службы: https://api.security.microsoft.com <br>

>[!NOTE]
>Для повышения производительности можно использовать сервер ближе к географическому расположению:
> - api-us.security.microsoft.com
> - api-eu.security.microsoft.com
> - api-uk.security.microsoft.com

 - Ресурс для получения маркера должен быть следующим: https://api.security.microsoft.com

 - Все API в ```/api``` пути являются API OData. т. ```https://api.security.microsoft.com/api/incidents```

## <a name="list-of-available-apis"></a>Список доступных API:

Статья | Описание
:---|:---
[Программный интерфейс расширенной охоты](api-advanced-hunting.md) | Выполнение расширенных запросов на поиск с API.
[Программные интерфейсы, относящиеся к инцидентам](api-incident.md) | Запускать вызовы API, связанные с инцидентами, такие как: Список инцидентов, обновление инцидента и многое другое.
