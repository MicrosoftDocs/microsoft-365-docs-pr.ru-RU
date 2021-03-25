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
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3760ff84e6abfbe05d9e4605d64087d0077300e3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071637"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="a8434-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="a8434-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a8434-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a8434-105">**Applies to:**</span></span>
- <span data-ttu-id="a8434-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a8434-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a8434-107">Используйте функцию в расширенных запросах для охоты, чтобы быстро получить последние IP-адреса, которые были назначены `AssignedIPAddresses()` устройству. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a8434-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="a8434-108">Если указать аргумент timestamp, эта функция получает самые последние IP-адреса в указанное время.</span><span class="sxs-lookup"><span data-stu-id="a8434-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="a8434-109">Эта функция возвращает таблицу со следующими столбцами:</span><span class="sxs-lookup"><span data-stu-id="a8434-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="a8434-110">Column</span><span class="sxs-lookup"><span data-stu-id="a8434-110">Column</span></span> | <span data-ttu-id="a8434-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a8434-111">Data type</span></span> | <span data-ttu-id="a8434-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a8434-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="a8434-113">datetime</span><span class="sxs-lookup"><span data-stu-id="a8434-113">datetime</span></span> | <span data-ttu-id="a8434-114">Последний раз, когда устройство было замечено с помощью IP-адреса</span><span class="sxs-lookup"><span data-stu-id="a8434-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="a8434-115">строка</span><span class="sxs-lookup"><span data-stu-id="a8434-115">string</span></span> | <span data-ttu-id="a8434-116">IP-адрес, используемый устройством</span><span class="sxs-lookup"><span data-stu-id="a8434-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="a8434-117">строка</span><span class="sxs-lookup"><span data-stu-id="a8434-117">string</span></span> | <span data-ttu-id="a8434-118">Указывает, является ли IP-адрес общедоступным или частным.</span><span class="sxs-lookup"><span data-stu-id="a8434-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="a8434-119">int</span><span class="sxs-lookup"><span data-stu-id="a8434-119">int</span></span> | <span data-ttu-id="a8434-120">Тип сетевого адаптер, используемый устройством, которое было назначено IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="a8434-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="a8434-121">Для возможных значений обратитесь к [этому переуме-](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="a8434-121">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="a8434-122">int</span><span class="sxs-lookup"><span data-stu-id="a8434-122">int</span></span> | <span data-ttu-id="a8434-123">Сети, к которые подключен адаптер с заявляемом IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="a8434-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="a8434-124">Каждый массив JSON содержит имя сети, категорию (общедоступный, частный или домен), описание и флаг, указывающий, подключен ли он публично к Интернету</span><span class="sxs-lookup"><span data-stu-id="a8434-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="a8434-125">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8434-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="a8434-126">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a8434-126">Arguments</span></span>

- <span data-ttu-id="a8434-127">**x**— `DeviceId` `DeviceName` или значение, определяющее устройство</span><span class="sxs-lookup"><span data-stu-id="a8434-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="a8434-128">**y**— (datetime) значение, предписывающие функции получать самые последние назначенные `Timestamp` IP-адреса в определенное время.</span><span class="sxs-lookup"><span data-stu-id="a8434-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="a8434-129">Если не указано, функция возвращает последние IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="a8434-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="a8434-130">Примеры</span><span class="sxs-lookup"><span data-stu-id="a8434-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="a8434-131">Получить список IP-адресов, используемых устройством 24 часа назад</span><span class="sxs-lookup"><span data-stu-id="a8434-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="a8434-132">Получите IP-адреса, используемые устройством, и найдите устройства, связывающие с ним</span><span class="sxs-lookup"><span data-stu-id="a8434-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="a8434-133">Этот запрос использует функцию для получения назначенного IP-адресов для устройства () на или `AssignedIPAddresses()` `example-device-name` до определенной даты ( `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="a8434-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="a8434-134">Затем он использует IP-адреса для поиска подключений к устройству, инициированного другими устройствами.</span><span class="sxs-lookup"><span data-stu-id="a8434-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="a8434-135">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a8434-135">Related topics</span></span>
- [<span data-ttu-id="a8434-136">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="a8434-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a8434-137">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="a8434-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a8434-138">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="a8434-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)