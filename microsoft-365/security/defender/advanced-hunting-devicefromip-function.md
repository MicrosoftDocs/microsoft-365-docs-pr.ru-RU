---
title: Функция DeviceFromIP() в продвинутой охоте для Microsoft 365 Defender
description: Узнайте, как использовать функцию DeviceFromIP() для получения устройств, которые были назначены определенному IP-адресу
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema reference, kusto, device, devicefromIP, function, enrichment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3ea951e35555721a989001b2a5235df5b89a8a55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933185"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Используйте `DeviceFromIP()` функцию [](advanced-hunting-overview.md) в расширенных запросах на охоту, чтобы быстро получить список устройств, которые были назначены определенному IP-адресу в определенный момент времени. 

Эта функция возвращает таблицу со следующими столбцами:

| Column | Тип данных | Описание |
|------------|-------------|-------------|
| `IP` | string | IP-адрес  |
| `DeviceId` | Строка | Уникальный идентификатор устройства в службе |


## <a name="syntax"></a>Синтаксис

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Аргументы

Эта функция вызывается в рамках запроса.

- **x**— первый параметр обычно уже является столбцом в запросе. В этом случае это столбец с именем , IP-адрес, для которого необходимо увидеть список устройств, которые были назначены `IP` ему. Это должен быть локальный IP-адрес. Внешние IP-адреса не поддерживаются.
- **y**— второй необязательный параметр — это параметр, который предписывает функции получать самые последние назначенные `Timestamp` устройства в определенное время. Если не указано, функция возвращает последние доступные записи.

## <a name="example"></a>Пример


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>Получите новейшие устройства, которые были назначены определенным IP-адресам

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>Похожие темы
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
