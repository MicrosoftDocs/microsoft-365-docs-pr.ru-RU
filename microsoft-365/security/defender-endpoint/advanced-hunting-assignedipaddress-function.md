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
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 5dcc41302d797b4084c36d020908ba59131c90d4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499288"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="3a15a-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="3a15a-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

><span data-ttu-id="3a15a-105">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="3a15a-105">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3a15a-106">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="3a15a-106">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="3a15a-107">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3a15a-107">**Applies to:**</span></span>
- [<span data-ttu-id="3a15a-108">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3a15a-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="3a15a-109">Используйте функцию в расширенных запросах для охоты, чтобы быстро получить последние IP-адреса, которые были назначены `AssignedIPAddresses()` устройству.</span><span class="sxs-lookup"><span data-stu-id="3a15a-109">Use the `AssignedIPAddresses()` function in your advanced hunting queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="3a15a-110">Если указать аргумент timestamp, эта функция получает самые последние IP-адреса в указанное время.</span><span class="sxs-lookup"><span data-stu-id="3a15a-110">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span>

<span data-ttu-id="3a15a-111">Эта функция возвращает таблицу со следующими столбцами:</span><span class="sxs-lookup"><span data-stu-id="3a15a-111">This function returns a table with the following columns:</span></span>

<span data-ttu-id="3a15a-112">Column</span><span class="sxs-lookup"><span data-stu-id="3a15a-112">Column</span></span> | <span data-ttu-id="3a15a-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="3a15a-113">Data type</span></span> | <span data-ttu-id="3a15a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3a15a-114">Description</span></span>
-|-|-
`Timestamp` | <span data-ttu-id="3a15a-115">datetime</span><span class="sxs-lookup"><span data-stu-id="3a15a-115">datetime</span></span> | <span data-ttu-id="3a15a-116">Последний раз, когда устройство было замечено с помощью IP-адреса</span><span class="sxs-lookup"><span data-stu-id="3a15a-116">Latest time when the device was observed using the IP address</span></span>
`IPAddress` | <span data-ttu-id="3a15a-117">string</span><span class="sxs-lookup"><span data-stu-id="3a15a-117">string</span></span> | <span data-ttu-id="3a15a-118">IP-адрес, используемый устройством</span><span class="sxs-lookup"><span data-stu-id="3a15a-118">IP address used by the device</span></span>
`IPType` | <span data-ttu-id="3a15a-119">string</span><span class="sxs-lookup"><span data-stu-id="3a15a-119">string</span></span> | <span data-ttu-id="3a15a-120">Указывает, является ли IP-адрес общедоступным или частным.</span><span class="sxs-lookup"><span data-stu-id="3a15a-120">Indicates whether the IP address is a public or private address</span></span>
`NetworkAdapterType` | <span data-ttu-id="3a15a-121">int</span><span class="sxs-lookup"><span data-stu-id="3a15a-121">int</span></span> | <span data-ttu-id="3a15a-122">Тип сетевого адаптер, используемый устройством, которое было назначено IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="3a15a-122">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="3a15a-123">Для возможных значений обратитесь к [этому переуме-](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="3a15a-123">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span>
`ConnectedNetworks` | <span data-ttu-id="3a15a-124">int</span><span class="sxs-lookup"><span data-stu-id="3a15a-124">int</span></span> | <span data-ttu-id="3a15a-125">Сети, к которые подключен адаптер с заявляемом IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="3a15a-125">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="3a15a-126">Каждый массив JSON содержит имя сети, категорию (общедоступный, частный или домен), описание и флаг, указывающий, подключен ли он публично к Интернету</span><span class="sxs-lookup"><span data-stu-id="3a15a-126">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span>

## <a name="syntax"></a><span data-ttu-id="3a15a-127">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a15a-127">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="3a15a-128">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3a15a-128">Arguments</span></span>

- <span data-ttu-id="3a15a-129">**x**— `DeviceId` `DeviceName` или значение, определяющее устройство</span><span class="sxs-lookup"><span data-stu-id="3a15a-129">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="3a15a-130">**y**— (datetime) значение, предписывающие функции получать самые последние назначенные `Timestamp` IP-адреса в определенное время.</span><span class="sxs-lookup"><span data-stu-id="3a15a-130">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="3a15a-131">Если не указано, функция возвращает последние IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="3a15a-131">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="3a15a-132">Примеры</span><span class="sxs-lookup"><span data-stu-id="3a15a-132">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="3a15a-133">Получить список IP-адресов, используемых устройством 24 часа назад</span><span class="sxs-lookup"><span data-stu-id="3a15a-133">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="3a15a-134">Получите IP-адреса, используемые устройством, и найдите устройства, связывающие с ним</span><span class="sxs-lookup"><span data-stu-id="3a15a-134">Get IP addresses used by a device and find devices communicating with it</span></span>

<span data-ttu-id="3a15a-135">Этот запрос использует функцию для получения назначенного IP-адресов для устройства () на или `AssignedIPAddresses()` `example-device-name` до определенной даты ( `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="3a15a-135">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="3a15a-136">Затем он использует IP-адреса для поиска подключений к устройству, инициированного другими устройствами.</span><span class="sxs-lookup"><span data-stu-id="3a15a-136">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="3a15a-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3a15a-137">Related topics</span></span>

- [<span data-ttu-id="3a15a-138">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="3a15a-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3a15a-139">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="3a15a-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3a15a-140">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="3a15a-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
