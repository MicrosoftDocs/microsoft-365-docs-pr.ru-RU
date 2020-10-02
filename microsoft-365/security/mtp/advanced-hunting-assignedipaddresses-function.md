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
ms.openlocfilehash: ea6b65e5e6d676c5efb2622193197bae5b9ba1b2
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338549"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="bf5c1-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="bf5c1-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bf5c1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="bf5c1-105">**Applies to:**</span></span>
- <span data-ttu-id="bf5c1-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="bf5c1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="bf5c1-107">Используйте `AssignedIPAddresses()` функцию в [расширенных](advanced-hunting-overview.md) запросах на поиск для быстрого получения последних IP-адресов, назначенных устройству.</span><span class="sxs-lookup"><span data-stu-id="bf5c1-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="bf5c1-108">Если указать аргумент timestamp, эта функция получает самые последние IP-адреса в указанное время.</span><span class="sxs-lookup"><span data-stu-id="bf5c1-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="bf5c1-109">Эта функция возвращает таблицу со следующими столбцами:</span><span class="sxs-lookup"><span data-stu-id="bf5c1-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="bf5c1-110">Столбец</span><span class="sxs-lookup"><span data-stu-id="bf5c1-110">Column</span></span> | <span data-ttu-id="bf5c1-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="bf5c1-111">Data type</span></span> | <span data-ttu-id="bf5c1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bf5c1-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="bf5c1-113">datetime</span><span class="sxs-lookup"><span data-stu-id="bf5c1-113">datetime</span></span> | <span data-ttu-id="bf5c1-114">Время последнего обнаружения устройства с помощью IP-адреса</span><span class="sxs-lookup"><span data-stu-id="bf5c1-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="bf5c1-115">string</span><span class="sxs-lookup"><span data-stu-id="bf5c1-115">string</span></span> | <span data-ttu-id="bf5c1-116">IP-адрес, используемый устройством</span><span class="sxs-lookup"><span data-stu-id="bf5c1-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="bf5c1-117">string</span><span class="sxs-lookup"><span data-stu-id="bf5c1-117">string</span></span> | <span data-ttu-id="bf5c1-118">Указывает, является ли IP-адрес общедоступным или частным адресом</span><span class="sxs-lookup"><span data-stu-id="bf5c1-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="bf5c1-119">int</span><span class="sxs-lookup"><span data-stu-id="bf5c1-119">int</span></span> | <span data-ttu-id="bf5c1-120">Тип сетевого адаптера, используемый устройством, которому назначен IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="bf5c1-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="bf5c1-121">Чтобы получить возможные значения, обратитесь к [этому перечислению](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="bf5c1-121">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="bf5c1-122">int</span><span class="sxs-lookup"><span data-stu-id="bf5c1-122">int</span></span> | <span data-ttu-id="bf5c1-123">Сети, к которым подключен адаптер с назначенным IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="bf5c1-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="bf5c1-124">Каждый массив JSON содержит имя сети, категорию (общедоступный, частный или доменный), описание и флаг, указывающий, подключен ли он к Интернету общедоступным</span><span class="sxs-lookup"><span data-stu-id="bf5c1-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="bf5c1-125">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf5c1-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="bf5c1-126">Аргументы</span><span class="sxs-lookup"><span data-stu-id="bf5c1-126">Arguments</span></span>

- <span data-ttu-id="bf5c1-127">**x**— `DeviceId` или `DeviceName` значение, идентифицирующее устройство</span><span class="sxs-lookup"><span data-stu-id="bf5c1-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="bf5c1-128">**y**— `Timestamp` значение DateTime, указывающее функции получить последние назначенные IP-адреса с определенного момента времени.</span><span class="sxs-lookup"><span data-stu-id="bf5c1-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="bf5c1-129">Если этот параметр не указан, функция возвращает последние IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="bf5c1-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="bf5c1-130">Примеры</span><span class="sxs-lookup"><span data-stu-id="bf5c1-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="bf5c1-131">Получение списка IP-адресов, используемых устройством через 24 часа назад</span><span class="sxs-lookup"><span data-stu-id="bf5c1-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="bf5c1-132">Получение IP-адресов, используемых устройством, и поиск устройств, взаимодействующих с ним</span><span class="sxs-lookup"><span data-stu-id="bf5c1-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="bf5c1-133">Этот запрос использует `AssignedIPAddresses()` функцию для получения назначенных IP-адресов для устройства ( `example-device-name` ) в указанную дату или до нее () `example-date` .</span><span class="sxs-lookup"><span data-stu-id="bf5c1-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="bf5c1-134">Затем он использует IP-адреса для поиска подключений к устройству, инициированному другими устройствами.</span><span class="sxs-lookup"><span data-stu-id="bf5c1-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="bf5c1-135">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="bf5c1-135">Related topics</span></span>
- [<span data-ttu-id="bf5c1-136">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="bf5c1-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bf5c1-137">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="bf5c1-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bf5c1-138">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="bf5c1-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
