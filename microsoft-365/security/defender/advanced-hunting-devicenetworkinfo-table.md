---
title: Таблица DeviceNetworkInfo в продвинутой схеме охоты
description: Сведения о конфигурации сети в таблице DeviceNetworkInfo в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, adapter, dns, dhcp, gateway, tunnel
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
ms.openlocfilehash: 11a6fd00524e3dd7ad456f68da6f493d74deee69
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023195"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="84af9-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="84af9-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="84af9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="84af9-105">**Applies to:**</span></span>
- <span data-ttu-id="84af9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84af9-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="84af9-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="84af9-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="84af9-108">Таблица в продвинутой схеме охоты содержит сведения о конфигурации сетевых компьютеров, включая сетевые адаптеры, IP-адреса и MAC, подключенные сети или `DeviceNetworkInfo` домены. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="84af9-108">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="84af9-109">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="84af9-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="84af9-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="84af9-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="84af9-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="84af9-111">Column name</span></span> | <span data-ttu-id="84af9-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="84af9-112">Data type</span></span> | <span data-ttu-id="84af9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="84af9-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="84af9-114">datetime</span><span class="sxs-lookup"><span data-stu-id="84af9-114">datetime</span></span> | <span data-ttu-id="84af9-115">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="84af9-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="84af9-116">string</span><span class="sxs-lookup"><span data-stu-id="84af9-116">string</span></span> | <span data-ttu-id="84af9-117">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="84af9-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="84af9-118">string</span><span class="sxs-lookup"><span data-stu-id="84af9-118">string</span></span> | <span data-ttu-id="84af9-119">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="84af9-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="84af9-120">string</span><span class="sxs-lookup"><span data-stu-id="84af9-120">string</span></span> | <span data-ttu-id="84af9-121">Имя сетевого адаптер</span><span class="sxs-lookup"><span data-stu-id="84af9-121">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="84af9-122">Строка</span><span class="sxs-lookup"><span data-stu-id="84af9-122">string</span></span> | <span data-ttu-id="84af9-123">MAC-адрес сетевого адаптер</span><span class="sxs-lookup"><span data-stu-id="84af9-123">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="84af9-124">Строка</span><span class="sxs-lookup"><span data-stu-id="84af9-124">string</span></span> | <span data-ttu-id="84af9-125">Тип сетевого адаптер.</span><span class="sxs-lookup"><span data-stu-id="84af9-125">Network adapter type.</span></span> <span data-ttu-id="84af9-126">Для возможных значений обратитесь к [этому переуме-](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="84af9-126">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="84af9-127">Строка</span><span class="sxs-lookup"><span data-stu-id="84af9-127">string</span></span> | <span data-ttu-id="84af9-128">Состояние сетевого адаптер.</span><span class="sxs-lookup"><span data-stu-id="84af9-128">Operational status of the network adapter.</span></span> <span data-ttu-id="84af9-129">Для возможных значений обратитесь к [этому переуме-](/dotnet/api/system.net.networkinformation.operationalstatus)</span><span class="sxs-lookup"><span data-stu-id="84af9-129">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus)</span></span> |
| `TunnelType` | <span data-ttu-id="84af9-130">Строка</span><span class="sxs-lookup"><span data-stu-id="84af9-130">string</span></span> | <span data-ttu-id="84af9-131">Протокол туннеля, если интерфейс используется для этой цели, например 6to4, Teredo, ISATAP, PPTP, SSTP и SSH.</span><span class="sxs-lookup"><span data-stu-id="84af9-131">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="84af9-132">Строка</span><span class="sxs-lookup"><span data-stu-id="84af9-132">string</span></span> | <span data-ttu-id="84af9-133">Сети, к которые подключен адаптер.</span><span class="sxs-lookup"><span data-stu-id="84af9-133">Networks that the adapter is connected to.</span></span> <span data-ttu-id="84af9-134">Каждый массив JSON содержит имя сети, категорию (общедоступный, частный или домен), описание и флаг, указывающий, подключен ли он публично к Интернету</span><span class="sxs-lookup"><span data-stu-id="84af9-134">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="84af9-135">Строка</span><span class="sxs-lookup"><span data-stu-id="84af9-135">string</span></span> | <span data-ttu-id="84af9-136">Адреса DNS-серверов в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="84af9-136">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="84af9-137">Строка</span><span class="sxs-lookup"><span data-stu-id="84af9-137">string</span></span> | <span data-ttu-id="84af9-138">IPv4 адрес сервера DHCP</span><span class="sxs-lookup"><span data-stu-id="84af9-138">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="84af9-139">Строка</span><span class="sxs-lookup"><span data-stu-id="84af9-139">string</span></span> | <span data-ttu-id="84af9-140">IPv6 адрес сервера DHCP</span><span class="sxs-lookup"><span data-stu-id="84af9-140">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="84af9-141">Строка</span><span class="sxs-lookup"><span data-stu-id="84af9-141">string</span></span> | <span data-ttu-id="84af9-142">Адреса шлюзов по умолчанию в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="84af9-142">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="84af9-143">Строка</span><span class="sxs-lookup"><span data-stu-id="84af9-143">string</span></span> | <span data-ttu-id="84af9-144">Массив JSON, содержащий все IP-адреса, присвоенные адаптеру, а также соответствующий префикс подсети и пространство IP-адресов, таких как общедоступный, частный или ссылка-локальный.</span><span class="sxs-lookup"><span data-stu-id="84af9-144">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="84af9-145">long</span><span class="sxs-lookup"><span data-stu-id="84af9-145">long</span></span> | <span data-ttu-id="84af9-146">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="84af9-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="84af9-147">Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp.</span><span class="sxs-lookup"><span data-stu-id="84af9-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="84af9-148">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="84af9-148">Related topics</span></span>
- [<span data-ttu-id="84af9-149">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="84af9-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="84af9-150">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="84af9-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="84af9-151">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="84af9-151">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="84af9-152">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="84af9-152">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="84af9-153">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="84af9-153">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="84af9-154">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="84af9-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)