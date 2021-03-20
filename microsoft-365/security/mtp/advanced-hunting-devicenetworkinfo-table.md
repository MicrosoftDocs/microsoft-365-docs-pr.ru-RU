---
title: Таблица DeviceNetworkInfo в продвинутой схеме охоты
description: Сведения о конфигурации сети в таблице DeviceNetworkInfo в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, ссылка схемы, kusto, таблица, столбец, тип данных, описание, machinenetworkinfo, DeviceNetworkInfo, устройство, машина, mac, ip, адаптер, dns, dhcp, шлюз, туннель
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
ms.openlocfilehash: 3e3b657d1c33e411f38a8f583adb96139cc85207
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907400"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="26b89-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="26b89-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="26b89-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="26b89-105">**Applies to:**</span></span>
- <span data-ttu-id="26b89-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26b89-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="26b89-107">Таблица в продвинутой схеме охоты содержит сведения о конфигурации сетевых компьютеров, включая сетевые адаптеры, IP-адреса и MAC, подключенные сети или `DeviceNetworkInfo` домены. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="26b89-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="26b89-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="26b89-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="26b89-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="26b89-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="26b89-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="26b89-110">Column name</span></span> | <span data-ttu-id="26b89-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="26b89-111">Data type</span></span> | <span data-ttu-id="26b89-112">Описание</span><span class="sxs-lookup"><span data-stu-id="26b89-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="26b89-113">datetime</span><span class="sxs-lookup"><span data-stu-id="26b89-113">datetime</span></span> | <span data-ttu-id="26b89-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="26b89-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="26b89-115">string</span><span class="sxs-lookup"><span data-stu-id="26b89-115">string</span></span> | <span data-ttu-id="26b89-116">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="26b89-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="26b89-117">string</span><span class="sxs-lookup"><span data-stu-id="26b89-117">string</span></span> | <span data-ttu-id="26b89-118">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="26b89-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="26b89-119">long</span><span class="sxs-lookup"><span data-stu-id="26b89-119">long</span></span> | <span data-ttu-id="26b89-120">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="26b89-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="26b89-121">Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp.</span><span class="sxs-lookup"><span data-stu-id="26b89-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="26b89-122">string</span><span class="sxs-lookup"><span data-stu-id="26b89-122">string</span></span> | <span data-ttu-id="26b89-123">Имя сетевого адаптер</span><span class="sxs-lookup"><span data-stu-id="26b89-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="26b89-124">string</span><span class="sxs-lookup"><span data-stu-id="26b89-124">string</span></span> | <span data-ttu-id="26b89-125">MAC-адрес сетевого адаптер</span><span class="sxs-lookup"><span data-stu-id="26b89-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="26b89-126">string</span><span class="sxs-lookup"><span data-stu-id="26b89-126">string</span></span> | <span data-ttu-id="26b89-127">Тип сетевого адаптер.</span><span class="sxs-lookup"><span data-stu-id="26b89-127">Network adapter type.</span></span> <span data-ttu-id="26b89-128">Для возможных значений обратитесь к [этому переуме-](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="26b89-128">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="26b89-129">string</span><span class="sxs-lookup"><span data-stu-id="26b89-129">string</span></span> | <span data-ttu-id="26b89-130">Состояние сетевого адаптер.</span><span class="sxs-lookup"><span data-stu-id="26b89-130">Operational status of the network adapter.</span></span> <span data-ttu-id="26b89-131">Для возможных значений обратитесь к [этому переуме-](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="26b89-131">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="26b89-132">string</span><span class="sxs-lookup"><span data-stu-id="26b89-132">string</span></span> | <span data-ttu-id="26b89-133">Протокол туннеля, если интерфейс используется для этой цели, например 6to4, Teredo, ISATAP, PPTP, SSTP и SSH.</span><span class="sxs-lookup"><span data-stu-id="26b89-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="26b89-134">string</span><span class="sxs-lookup"><span data-stu-id="26b89-134">string</span></span> | <span data-ttu-id="26b89-135">Сети, к которые подключен адаптер.</span><span class="sxs-lookup"><span data-stu-id="26b89-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="26b89-136">Каждый массив JSON содержит имя сети, категорию (общедоступный, частный или домен), описание и флаг, указывающий, подключен ли он публично к Интернету</span><span class="sxs-lookup"><span data-stu-id="26b89-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="26b89-137">string</span><span class="sxs-lookup"><span data-stu-id="26b89-137">string</span></span> | <span data-ttu-id="26b89-138">Адреса DNS-серверов в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="26b89-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="26b89-139">string</span><span class="sxs-lookup"><span data-stu-id="26b89-139">string</span></span> | <span data-ttu-id="26b89-140">IPv4 адрес сервера DHCP</span><span class="sxs-lookup"><span data-stu-id="26b89-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="26b89-141">string</span><span class="sxs-lookup"><span data-stu-id="26b89-141">string</span></span> | <span data-ttu-id="26b89-142">IPv6 адрес сервера DHCP</span><span class="sxs-lookup"><span data-stu-id="26b89-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="26b89-143">string</span><span class="sxs-lookup"><span data-stu-id="26b89-143">string</span></span> | <span data-ttu-id="26b89-144">Адреса шлюзов по умолчанию в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="26b89-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="26b89-145">string</span><span class="sxs-lookup"><span data-stu-id="26b89-145">string</span></span> | <span data-ttu-id="26b89-146">Массив JSON, содержащий все IP-адреса, присвоенные адаптеру, а также соответствующий префикс подсети и пространство IP-адресов, таких как общедоступный, частный или ссылка-локальный.</span><span class="sxs-lookup"><span data-stu-id="26b89-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="26b89-147">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="26b89-147">Related topics</span></span>
- [<span data-ttu-id="26b89-148">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="26b89-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="26b89-149">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="26b89-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="26b89-150">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="26b89-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="26b89-151">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="26b89-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="26b89-152">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="26b89-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="26b89-153">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="26b89-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)