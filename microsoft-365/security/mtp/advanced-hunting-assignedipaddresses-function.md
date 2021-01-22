---
title: Функция AssignedIPAddresses() в advanced hunting for Microsoft 365 Defender
description: Узнайте, как использовать функцию AssignedIPAddresses() для получения последних IP-адресов, присвоенных устройству
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
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
ms.openlocfilehash: d16cd7efc49cc2498eff3f705bb43fa62f37d975
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933022"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Используйте функцию в расширенных запросах на поиск, чтобы быстро получить последние IP-адреса, которые были назначены `AssignedIPAddresses()` устройству. [](advanced-hunting-overview.md) Если указан аргумент timestamp, эта функция получает самые последние IP-адреса в указанное время. 

Эта функция возвращает таблицу со следующими столбцами:

| Столбец | Тип данных | Описание |
|------------|-------------|-------------|
| `Timestamp` | datetime | Последнее время, когда устройство наблюдалось с использованием IP-адреса |
| `IPAddress` | string | IP-адрес, используемый устройством |
| `IPType` | string | Указывает, является ли IP-адрес общедоступным или частным. |
| `NetworkAdapterType` | int | Тип сетевого адаптера, используемого устройством, которое было назначено IP-адресу. Возможные значения: [](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | Сети, к которые подключен адаптер с ip-адресом. Каждый массив JSON содержит имя сети, категорию (общедоступный, частный или домен), описание и флаг, указывающий, подключен ли он к Интернету общедоступным образом. |

## <a name="syntax"></a>Синтаксис

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Аргументы

- **x**— `DeviceId` или `DeviceName` значение, идентифицирующее устройство
- **y**— значение даты и времени, указывав функции на получение самых последних `Timestamp` назначенных IP-адресов за определенное время. Если этот адрес не указан, функция возвращает последние IP-адреса.

## <a name="examples"></a>Примеры

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Получить список IP-адресов, используемых устройством 24 часа назад

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Получите IP-адреса, используемые устройством, и найдите устройства, которые с ним общаются
Этот запрос использует функцию для получения IP-адресов, которые назначены устройству ( ) до `AssignedIPAddresses()` `example-device-name` определенной даты ( `example-date` ). Затем он использует IP-адреса для поиска подключений к устройству, инициированных другими устройствами. 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
