---
title: Функция AssignedIPAddresses() в продвинутой охоте для Microsoft 365 Defender
description: Узнайте, как использовать функцию AssignedIPAddresses() для получения последних IP-адресов, присвоенных устройству
keywords: передовая охота, охота на угрозы, поиск киберугроз, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, ссылка схемы, kusto, FileProfile, профиль файла, функция, обогащение
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
ms.openlocfilehash: be638141e205946be18d6a718470e7b92b18b1e7
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500410"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Используйте функцию в расширенных запросах для охоты, чтобы быстро получить последние IP-адреса, которые были назначены `AssignedIPAddresses()` устройству. [](advanced-hunting-overview.md) Если указать аргумент timestamp, эта функция получает самые последние IP-адреса в указанное время. 

Эта функция возвращает таблицу со следующими столбцами:

| Column | Тип данных | Описание |
|------------|-------------|-------------|
| `Timestamp` | datetime | Последний раз, когда устройство было замечено с помощью IP-адреса |
| `IPAddress` | string | IP-адрес, используемый устройством |
| `IPType` | string | Указывает, является ли IP-адрес общедоступным или частным. |
| `NetworkAdapterType` | int | Тип сетевого адаптер, используемый устройством, которое было назначено IP-адресу. Для возможных значений обратитесь к [этому переуме-](/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | Сети, к которые подключен адаптер с заявляемом IP-адресом. Каждый массив JSON содержит имя сети, категорию (общедоступный, частный или домен), описание и флаг, указывающий, подключен ли он публично к Интернету |

## <a name="syntax"></a>Синтаксис

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Аргументы

- **x**— `DeviceId` `DeviceName` или значение, определяющее устройство
- **y**— (datetime) значение, предписывающие функции получать самые последние назначенные `Timestamp` IP-адреса в определенное время. Если не указано, функция возвращает последние IP-адреса.

## <a name="examples"></a>Примеры

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Получить список IP-адресов, используемых устройством 24 часа назад

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Получите IP-адреса, используемые устройством, и найдите устройства, связывающие с ним
Этот запрос использует функцию для получения назначенного IP-адресов для устройства () на или `AssignedIPAddresses()` `example-device-name` до определенной даты ( `example-date` ). Затем он использует IP-адреса для поиска подключений к устройству, инициированного другими устройствами. 

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
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)