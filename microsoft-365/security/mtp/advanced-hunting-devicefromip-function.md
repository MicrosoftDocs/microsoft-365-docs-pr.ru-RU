---
title: Функция DeviceFromIP() в advanced hunting for Microsoft 365 Defender
description: Узнайте, как использовать функцию DeviceFromIP() для получения устройств, которые были назначены определенному IP-адресу
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, device, devicefromIP, function, enrichment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 65409dd93f3703f1af115178c4cd9fa470fb7497
ms.sourcegitcommit: 25ac2736a66bb72c0d574c3fbde7472ac98d5321
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2020
ms.locfileid: "49741116"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Используйте `DeviceFromIP()` функцию [](advanced-hunting-overview.md) в расширенных запросах на поиск, чтобы быстро получить список устройств, которые были назначены определенному IP-адресу в определенный момент времени. 

Эта функция возвращает таблицу со следующими столбцами:

| Столбец | Тип данных | Описание |
|------------|-------------|-------------|
| `IP` | string | IP-адрес  |
| `DeviceId` | string | Уникальный идентификатор устройства в службе |


## <a name="syntax"></a>Синтаксис

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Аргументы

Эта функция вызывается как часть запроса.

- **x**— первый параметр обычно уже является столбцом в запросе. В этом случае это столбец с именем IP-адрес, для которого вы хотите увидеть список устройств, которые ему `IP` назначены. Это должен быть локальный IP-адрес. Внешние IP-адреса не поддерживаются.
- **y**— второй необязательный параметр — это параметр, который сообщает функции о получении последних устройств с `Timestamp` определенного времени. Если не указано, функция возвращает последние доступные записи.

## <a name="example"></a>Пример


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>Получить последние устройства, для которые были назначены определенные IP-адреса

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
