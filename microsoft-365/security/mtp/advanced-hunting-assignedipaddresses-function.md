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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 72d02bafa168e48c2d588771f5289da09e6d6000
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794235"
---
# <a name="assignedipaddresses"></a>Ассигнедипаддрессес ()

**Область применения:**
- Защита от угроз (Майкрософт)

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Используйте `AssignedIPAddresses()` функцию для быстрого получения последних IP-адресов, назначенных устройству или последним IP-адресам из указанного момента времени. Эта функция возвращает таблицу со следующими столбцами:

| Столбец | Тип данных | Описание |
|------------|-------------|-------------|
| Timestamp | datetime | Время последнего обнаружения устройства с помощью IP-адреса |
| IPAddress | string | IP-адрес, используемый устройством |
| иптипе | string | Указывает, является ли IP-адрес общедоступным или частным адресом |
| нетворкадаптертипе | int | Тип сетевого адаптера, используемый устройством, которому назначен IP-адрес. Чтобы получить возможные значения, обратитесь к [этому перечислению](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)  |
| коннектеднетворкс | int | Сети, к которым подключен адаптер с назначенным IP-адресом. Каждый массив JSON содержит имя сети, категорию (общедоступное, частное, частное или доменное), описание и флаг, указывающий, подключен ли он к Интернету общедоступным |


## <a name="syntax"></a>Синтаксис

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Аргументы

- **x** — `DeviceId` или `DeviceName` значение, идентифицирующее устройство
- значение **y** — `Timestamp` (DateTime), указывающее конкретный момент времени, где можно получить самые последние IP-адреса. Если этот параметр не указан, функция возвращает последние IP-адреса.

## <a name="examples"></a>Примеры

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a>Получение списка IP-адресов, используемых устройством на 24 часа назад

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

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)