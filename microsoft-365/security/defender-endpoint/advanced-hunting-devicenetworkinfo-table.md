---
title: Таблица DeviceNetworkInfo в продвинутой схеме охоты
description: Сведения о конфигурации сети в таблице DeviceNetworkInfo в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, devicenetworkinfo, device, device, mac, ip, adapter, dns, dhcp, gateway, tunnel, DeviceNetworkInfo
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
ms.technology: mde
ms.openlocfilehash: e63af4153804a09424c36fb03ac715da5f6d9485
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499138"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="cc9f9-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="cc9f9-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cc9f9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="cc9f9-105">**Applies to:**</span></span>
- [<span data-ttu-id="cc9f9-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="cc9f9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="cc9f9-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="cc9f9-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cc9f9-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="cc9f9-109">Таблица в продвинутой схеме охоты содержит сведения о конфигурации сетевых устройств, включая сетевые адаптеры, IP-адреса и MAC, подключенные сети или `DeviceNetworkInfo` домены. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cc9f9-109">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of devices, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="cc9f9-110">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="cc9f9-111">Сведения о других таблицах в продвинутой схеме охоты см. в справке [о схеме охоты.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="cc9f9-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="cc9f9-112">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="cc9f9-112">Column name</span></span> | <span data-ttu-id="cc9f9-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="cc9f9-113">Data type</span></span> | <span data-ttu-id="cc9f9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="cc9f9-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="cc9f9-115">datetime</span><span class="sxs-lookup"><span data-stu-id="cc9f9-115">datetime</span></span> | <span data-ttu-id="cc9f9-116">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="cc9f9-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="cc9f9-117">string</span><span class="sxs-lookup"><span data-stu-id="cc9f9-117">string</span></span> | <span data-ttu-id="cc9f9-118">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="cc9f9-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="cc9f9-119">string</span><span class="sxs-lookup"><span data-stu-id="cc9f9-119">string</span></span> | <span data-ttu-id="cc9f9-120">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="cc9f9-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ReportId` | <span data-ttu-id="cc9f9-121">long</span><span class="sxs-lookup"><span data-stu-id="cc9f9-121">long</span></span> | <span data-ttu-id="cc9f9-122">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-122">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="cc9f9-123">Чтобы определить уникальные события, этот столбец должен использоваться совместно с `DeviceName` `Timestamp` столбцами и</span><span class="sxs-lookup"><span data-stu-id="cc9f9-123">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="cc9f9-124">string</span><span class="sxs-lookup"><span data-stu-id="cc9f9-124">string</span></span> | <span data-ttu-id="cc9f9-125">Имя сетевого адаптер</span><span class="sxs-lookup"><span data-stu-id="cc9f9-125">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="cc9f9-126">string</span><span class="sxs-lookup"><span data-stu-id="cc9f9-126">string</span></span> | <span data-ttu-id="cc9f9-127">MAC-адрес сетевого адаптер</span><span class="sxs-lookup"><span data-stu-id="cc9f9-127">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="cc9f9-128">string</span><span class="sxs-lookup"><span data-stu-id="cc9f9-128">string</span></span> | <span data-ttu-id="cc9f9-129">Тип сетевого адаптер.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-129">Network adapter type.</span></span> <span data-ttu-id="cc9f9-130">Для возможных значений обратитесь к [этому переуме-](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="cc9f9-130">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="cc9f9-131">string</span><span class="sxs-lookup"><span data-stu-id="cc9f9-131">string</span></span> | <span data-ttu-id="cc9f9-132">Состояние сетевого адаптер.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-132">Operational status of the network adapter.</span></span> <span data-ttu-id="cc9f9-133">Для возможных значений обратитесь к [этому переуме-](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="cc9f9-133">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `TunnelType` | <span data-ttu-id="cc9f9-134">string</span><span class="sxs-lookup"><span data-stu-id="cc9f9-134">string</span></span> | <span data-ttu-id="cc9f9-135">Протокол туннеля, если интерфейс используется для этой цели, например 6to4, Teredo, ISATAP, PPTP, SSTP и SSH.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-135">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="cc9f9-136">string</span><span class="sxs-lookup"><span data-stu-id="cc9f9-136">string</span></span> | <span data-ttu-id="cc9f9-137">Сети, к которые подключен адаптер.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-137">Networks that the adapter is connected to.</span></span> <span data-ttu-id="cc9f9-138">Каждый массив JSON содержит имя сети, категорию (общедоступный, частный или домен), описание и флаг, указывающий, подключен ли он публично к Интернету</span><span class="sxs-lookup"><span data-stu-id="cc9f9-138">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="cc9f9-139">string</span><span class="sxs-lookup"><span data-stu-id="cc9f9-139">string</span></span> | <span data-ttu-id="cc9f9-140">Адреса DNS-серверов в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="cc9f9-140">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="cc9f9-141">string</span><span class="sxs-lookup"><span data-stu-id="cc9f9-141">string</span></span> | <span data-ttu-id="cc9f9-142">IPv4 адрес сервера DHCP</span><span class="sxs-lookup"><span data-stu-id="cc9f9-142">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="cc9f9-143">string</span><span class="sxs-lookup"><span data-stu-id="cc9f9-143">string</span></span> | <span data-ttu-id="cc9f9-144">IPv6 адрес сервера DHCP</span><span class="sxs-lookup"><span data-stu-id="cc9f9-144">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="cc9f9-145">string</span><span class="sxs-lookup"><span data-stu-id="cc9f9-145">string</span></span> | <span data-ttu-id="cc9f9-146">Адреса шлюзов по умолчанию в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="cc9f9-146">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="cc9f9-147">string</span><span class="sxs-lookup"><span data-stu-id="cc9f9-147">string</span></span> | <span data-ttu-id="cc9f9-148">Массив JSON, содержащий все IP-адреса, присвоенные адаптеру, а также соответствующий префикс подсети и пространство IP-адресов, таких как общедоступный, частный или ссылка-локальный.</span><span class="sxs-lookup"><span data-stu-id="cc9f9-148">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="cc9f9-149">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cc9f9-149">Related topics</span></span>
- [<span data-ttu-id="cc9f9-150">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="cc9f9-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cc9f9-151">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="cc9f9-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cc9f9-152">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="cc9f9-152">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
