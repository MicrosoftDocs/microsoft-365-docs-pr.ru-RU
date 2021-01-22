---
title: Таблица DeviceNetworkInfo в схеме advanced hunting
description: Сведения о конфигурации сети в таблице DeviceNetworkInfo схемы расширенных поисков
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, adapter, dns, dhcp, gateway, tunnel
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
ms.openlocfilehash: 9e2657631eb2ba8c784f38f76fad46166a450bf0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931210"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="15742-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="15742-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="15742-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="15742-105">**Applies to:**</span></span>
- <span data-ttu-id="15742-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15742-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="15742-107">Таблица в схеме advanced hunting содержит сведения о сетевой конфигурации компьютеров, включая сетевые адаптеры, IP-и MAC-адреса, а также подключенные сети `DeviceNetworkInfo` или домены. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="15742-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="15742-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="15742-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="15742-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="15742-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="15742-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="15742-110">Column name</span></span> | <span data-ttu-id="15742-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="15742-111">Data type</span></span> | <span data-ttu-id="15742-112">Описание</span><span class="sxs-lookup"><span data-stu-id="15742-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="15742-113">datetime</span><span class="sxs-lookup"><span data-stu-id="15742-113">datetime</span></span> | <span data-ttu-id="15742-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="15742-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="15742-115">string</span><span class="sxs-lookup"><span data-stu-id="15742-115">string</span></span> | <span data-ttu-id="15742-116">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="15742-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="15742-117">string</span><span class="sxs-lookup"><span data-stu-id="15742-117">string</span></span> | <span data-ttu-id="15742-118">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="15742-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="15742-119">long</span><span class="sxs-lookup"><span data-stu-id="15742-119">long</span></span> | <span data-ttu-id="15742-120">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="15742-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="15742-121">Чтобы определить уникальные события, этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp</span><span class="sxs-lookup"><span data-stu-id="15742-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="15742-122">string</span><span class="sxs-lookup"><span data-stu-id="15742-122">string</span></span> | <span data-ttu-id="15742-123">Имя сетевого адаптер</span><span class="sxs-lookup"><span data-stu-id="15742-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="15742-124">string</span><span class="sxs-lookup"><span data-stu-id="15742-124">string</span></span> | <span data-ttu-id="15742-125">MAC-адрес сетевого адаптера</span><span class="sxs-lookup"><span data-stu-id="15742-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="15742-126">string</span><span class="sxs-lookup"><span data-stu-id="15742-126">string</span></span> | <span data-ttu-id="15742-127">Тип сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="15742-127">Network adapter type.</span></span> <span data-ttu-id="15742-128">Возможные значения: [](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="15742-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="15742-129">string</span><span class="sxs-lookup"><span data-stu-id="15742-129">string</span></span> | <span data-ttu-id="15742-130">Операционное состояние сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="15742-130">Operational status of the network adapter.</span></span> <span data-ttu-id="15742-131">Возможные значения: [](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="15742-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="15742-132">string</span><span class="sxs-lookup"><span data-stu-id="15742-132">string</span></span> | <span data-ttu-id="15742-133">Протокол туннелинга, если интерфейс используется для этой цели, например 6to4, Teredo, ISATAP, PPTP, SSTP и SSH</span><span class="sxs-lookup"><span data-stu-id="15742-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="15742-134">string</span><span class="sxs-lookup"><span data-stu-id="15742-134">string</span></span> | <span data-ttu-id="15742-135">Сети, к которые подключен адаптер.</span><span class="sxs-lookup"><span data-stu-id="15742-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="15742-136">Каждый массив JSON содержит имя сети, категорию (общедоступный, частный или домен), описание и флаг, указывающий, подключен ли он к Интернету публично</span><span class="sxs-lookup"><span data-stu-id="15742-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="15742-137">string</span><span class="sxs-lookup"><span data-stu-id="15742-137">string</span></span> | <span data-ttu-id="15742-138">Адреса DNS-серверов в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="15742-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="15742-139">string</span><span class="sxs-lookup"><span data-stu-id="15742-139">string</span></span> | <span data-ttu-id="15742-140">IPv4-адрес DHCP-сервера</span><span class="sxs-lookup"><span data-stu-id="15742-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="15742-141">string</span><span class="sxs-lookup"><span data-stu-id="15742-141">string</span></span> | <span data-ttu-id="15742-142">IPv6-адрес DHCP-сервера</span><span class="sxs-lookup"><span data-stu-id="15742-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="15742-143">string</span><span class="sxs-lookup"><span data-stu-id="15742-143">string</span></span> | <span data-ttu-id="15742-144">Адреса шлюзов по умолчанию в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="15742-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="15742-145">string</span><span class="sxs-lookup"><span data-stu-id="15742-145">string</span></span> | <span data-ttu-id="15742-146">Массив JSON, содержащий все IP-адреса, присвоенные адаптеру, а также соответствующий префикс подсети и пространство IP-адресов, например общедоступный, частный или локальный</span><span class="sxs-lookup"><span data-stu-id="15742-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="15742-147">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="15742-147">Related topics</span></span>
- [<span data-ttu-id="15742-148">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="15742-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="15742-149">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="15742-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="15742-150">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="15742-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="15742-151">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="15742-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="15742-152">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="15742-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="15742-153">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="15742-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
