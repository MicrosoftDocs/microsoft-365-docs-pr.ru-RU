---
title: Поддерживаемые API защиты от угроз Майкрософт
description: Поддерживаемые API защиты от угроз Майкрософт
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
ms.openlocfilehash: 49fa182a6142748ca7769411fe74389f365ba75f
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650480"
---
# <a name="supported-microsoft-threat-protection-apis"></a>Поддерживаемые API защиты от угроз Майкрософт 
**Область применения:**
- Защита от угроз (Майкрософт)

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
[Расширенный поисковый API](api-advanced-hunting.md) | Выполнение расширенных запросов на поиск с API.
[API инцидентов](api-incident.md) | Запускать вызовы API, связанные с инцидентами, такие как: Список инцидентов, обновление инцидента и многое другое.
