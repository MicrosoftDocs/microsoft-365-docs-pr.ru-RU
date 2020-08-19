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
# <a name="assignedipaddresses"></a><span data-ttu-id="b5c8f-104">Ассигнедипаддрессес ()</span><span class="sxs-lookup"><span data-stu-id="b5c8f-104">AssignedIPAddresses()</span></span>

<span data-ttu-id="b5c8f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b5c8f-105">**Applies to:**</span></span>
- <span data-ttu-id="b5c8f-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b5c8f-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b5c8f-107">Используйте `AssignedIPAddresses()` функцию для быстрого получения последних IP-адресов, назначенных устройству или последним IP-адресам из указанного момента времени.</span><span class="sxs-lookup"><span data-stu-id="b5c8f-107">Use the `AssignedIPAddresses()` function to quickly obtain the latest IP addresses that have been assigned to a device or the most recent IP addresses from a specified point in time.</span></span> <span data-ttu-id="b5c8f-108">Эта функция возвращает таблицу со следующими столбцами:</span><span class="sxs-lookup"><span data-stu-id="b5c8f-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="b5c8f-109">Столбец</span><span class="sxs-lookup"><span data-stu-id="b5c8f-109">Column</span></span> | <span data-ttu-id="b5c8f-110">Тип данных</span><span class="sxs-lookup"><span data-stu-id="b5c8f-110">Data type</span></span> | <span data-ttu-id="b5c8f-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b5c8f-111">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="b5c8f-112">Timestamp</span><span class="sxs-lookup"><span data-stu-id="b5c8f-112">Timestamp</span></span> | <span data-ttu-id="b5c8f-113">datetime</span><span class="sxs-lookup"><span data-stu-id="b5c8f-113">datetime</span></span> | <span data-ttu-id="b5c8f-114">Время последнего обнаружения устройства с помощью IP-адреса</span><span class="sxs-lookup"><span data-stu-id="b5c8f-114">Latest time when the device was observed using the IP address</span></span> |
| <span data-ttu-id="b5c8f-115">IPAddress</span><span class="sxs-lookup"><span data-stu-id="b5c8f-115">IPAddress</span></span> | <span data-ttu-id="b5c8f-116">string</span><span class="sxs-lookup"><span data-stu-id="b5c8f-116">string</span></span> | <span data-ttu-id="b5c8f-117">IP-адрес, используемый устройством</span><span class="sxs-lookup"><span data-stu-id="b5c8f-117">IP address used by the device</span></span> |
| <span data-ttu-id="b5c8f-118">иптипе</span><span class="sxs-lookup"><span data-stu-id="b5c8f-118">IPType</span></span> | <span data-ttu-id="b5c8f-119">string</span><span class="sxs-lookup"><span data-stu-id="b5c8f-119">string</span></span> | <span data-ttu-id="b5c8f-120">Указывает, является ли IP-адрес общедоступным или частным адресом</span><span class="sxs-lookup"><span data-stu-id="b5c8f-120">Indicates whether the IP address is a public or private address</span></span> |
| <span data-ttu-id="b5c8f-121">нетворкадаптертипе</span><span class="sxs-lookup"><span data-stu-id="b5c8f-121">NetworkAdapterType</span></span> | <span data-ttu-id="b5c8f-122">int</span><span class="sxs-lookup"><span data-stu-id="b5c8f-122">int</span></span> | <span data-ttu-id="b5c8f-123">Тип сетевого адаптера, используемый устройством, которому назначен IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="b5c8f-123">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="b5c8f-124">Чтобы получить возможные значения, обратитесь к [этому перечислению](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="b5c8f-124">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span>  |
| <span data-ttu-id="b5c8f-125">коннектеднетворкс</span><span class="sxs-lookup"><span data-stu-id="b5c8f-125">ConnectedNetworks</span></span> | <span data-ttu-id="b5c8f-126">int</span><span class="sxs-lookup"><span data-stu-id="b5c8f-126">int</span></span> | <span data-ttu-id="b5c8f-127">Сети, к которым подключен адаптер с назначенным IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="b5c8f-127">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="b5c8f-128">Каждый массив JSON содержит имя сети, категорию (общедоступное, частное, частное или доменное), описание и флаг, указывающий, подключен ли он к Интернету общедоступным</span><span class="sxs-lookup"><span data-stu-id="b5c8f-128">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |


## <a name="syntax"></a><span data-ttu-id="b5c8f-129">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5c8f-129">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="b5c8f-130">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b5c8f-130">Arguments</span></span>

- <span data-ttu-id="b5c8f-131">**x** — `DeviceId` или `DeviceName` значение, идентифицирующее устройство</span><span class="sxs-lookup"><span data-stu-id="b5c8f-131">**x** — `DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="b5c8f-132">значение **y** — `Timestamp` (DateTime), указывающее конкретный момент времени, где можно получить самые последние IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="b5c8f-132">**y** — `Timestamp` (datetime) value indicating the specific point in time where to get the most recent IP addresses.</span></span> <span data-ttu-id="b5c8f-133">Если этот параметр не указан, функция возвращает последние IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="b5c8f-133">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="b5c8f-134">Примеры</span><span class="sxs-lookup"><span data-stu-id="b5c8f-134">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a><span data-ttu-id="b5c8f-135">Получение списка IP-адресов, используемых устройством на 24 часа назад</span><span class="sxs-lookup"><span data-stu-id="b5c8f-135">Get the list of IP addresses used by a device as of 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="b5c8f-136">Получение IP-адресов, используемых устройством, и поиск устройств, взаимодействующих с ним</span><span class="sxs-lookup"><span data-stu-id="b5c8f-136">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="b5c8f-137">Этот запрос использует `AssignedIPAddresses()` функцию для получения назначенных IP-адресов для устройства ( `example-device-name` ) в указанную дату или до нее () `example-date` .</span><span class="sxs-lookup"><span data-stu-id="b5c8f-137">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="b5c8f-138">Затем он использует IP-адреса для поиска подключений к устройству, инициированному другими устройствами.</span><span class="sxs-lookup"><span data-stu-id="b5c8f-138">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="b5c8f-139">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="b5c8f-139">Related topics</span></span>
- [<span data-ttu-id="b5c8f-140">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="b5c8f-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b5c8f-141">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="b5c8f-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b5c8f-142">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="b5c8f-142">Understand the schema</span></span>](advanced-hunting-schema-tables.md)