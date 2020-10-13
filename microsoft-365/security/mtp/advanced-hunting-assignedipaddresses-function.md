---
title: Функция Ассигнедипаддрессес () в расширенном поиске для защиты от угроз Майкрософт
description: Узнайте, как использовать функцию Ассигнедипаддрессес () для получения последних IP-адресов, назначенных устройству.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справочник по схемам, Кусто, Филепрофиле, профиле файла, функция, обогащение
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 462a4884e2b17f9ae75ea3bdc1531b180dcc5934
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430131"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)

Используйте `AssignedIPAddresses()` функцию в [расширенных](advanced-hunting-overview.md) запросах на поиск для быстрого получения последних IP-адресов, назначенных устройству. Если указать аргумент timestamp, эта функция получает самые последние IP-адреса в указанное время. 

Эта функция возвращает таблицу со следующими столбцами:

| Столбец | Тип данных | Описание |
|------------|-------------|-------------|
| `Timestamp` | datetime | Время последнего обнаружения устройства с помощью IP-адреса |
| `IPAddress` | string | IP-адрес, используемый устройством |
| `IPType` | string | Указывает, является ли IP-адрес общедоступным или частным адресом |
| `NetworkAdapterType` | int | Тип сетевого адаптера, используемый устройством, которому назначен IP-адрес. Чтобы получить возможные значения, обратитесь к [этому перечислению](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | Сети, к которым подключен адаптер с назначенным IP-адресом. Каждый массив JSON содержит имя сети, категорию (общедоступный, частный или доменный), описание и флаг, указывающий, подключен ли он к Интернету общедоступным |

## <a name="syntax"></a>Синтаксис

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Аргументы

- **x**— `DeviceId` или `DeviceName` значение, идентифицирующее устройство
- **y**— `Timestamp` значение DateTime, указывающее функции получить последние назначенные IP-адреса с определенного момента времени. Если этот параметр не указан, функция возвращает последние IP-адреса.

## <a name="examples"></a>Примеры

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Получение списка IP-адресов, используемых устройством через 24 часа назад

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Получение IP-адресов, используемых устройством, и поиск устройств, взаимодействующих с ним
Этот запрос использует `AssignedIPAddresses()` функцию для получения назначенных IP-адресов для устройства ( `example-device-name` ) в указанную дату или до нее () `example-date` . Затем он использует IP-адреса для поиска подключений к устройству, инициированному другими устройствами. 

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
