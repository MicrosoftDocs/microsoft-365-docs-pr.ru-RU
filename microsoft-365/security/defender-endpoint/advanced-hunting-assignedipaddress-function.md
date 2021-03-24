---
title: Функция AssignedIPAddresses() в продвинутой охоте для Microsoft Defender для конечной точки
description: Узнайте, как использовать функцию AssignedIPAddresses() для получения последних IP-адресов, присвоенных устройству
keywords: передовая охота, охота на угрозы, поиск киберугроз, mdatp, Microsoft Defender ATP, Microsoft Defender для endpoint, Защитник Windows, Защитник Windows ATP, Защитник Windows Advanced Threat Protection, search, query, telemetry, schema reference, kusto, FileProfile, fileProfile, file profile, function, enrichment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 08ab7ff5bac917a027e4380a46ab1cb2cf0a1312
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072437"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)


Используйте функцию в расширенных запросах для охоты, чтобы быстро получить последние IP-адреса, которые были назначены `AssignedIPAddresses()` устройству. Если указать аргумент timestamp, эта функция получает самые последние IP-адреса в указанное время.

Эта функция возвращает таблицу со следующими столбцами:

Column | Тип данных | Описание
-|-|-
`Timestamp` | datetime | Последний раз, когда устройство было замечено с помощью IP-адреса
`IPAddress` | строка | IP-адрес, используемый устройством
`IPType` | строка | Указывает, является ли IP-адрес общедоступным или частным.
`NetworkAdapterType` | int | Тип сетевого адаптер, используемый устройством, которое было назначено IP-адресу. Для возможных значений обратитесь к [этому переуме-](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)
`ConnectedNetworks` | int | Сети, к которые подключен адаптер с заявляемом IP-адресом. Каждый массив JSON содержит имя сети, категорию (общедоступный, частный или домен), описание и флаг, указывающий, подключен ли он публично к Интернету

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

- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
