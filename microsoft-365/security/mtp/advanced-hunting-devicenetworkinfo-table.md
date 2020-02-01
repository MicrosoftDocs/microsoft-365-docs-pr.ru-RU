---
title: Таблица девиценетворкинфо в схеме расширенного поискового окна
description: Сведения о конфигурации сети в таблице Девиценетворкинфо расширенной схемы подсистемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справочник по схемам, Кусто, таблица, столбец, тип данных, описание, мачиненетворкинфо, Девиценетворкинфо, устройство, компьютер, Mac, IP, адаптер, DNS, DHCP, шлюз, туннель
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
ms.openlocfilehash: 25349328cd128113de7846cba5c7c9ad74631092
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600416"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="3e189-104">девиценетворкинфо</span><span class="sxs-lookup"><span data-stu-id="3e189-104">DeviceNetworkInfo</span></span>

<span data-ttu-id="3e189-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3e189-105">**Applies to:**</span></span>
- <span data-ttu-id="3e189-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="3e189-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="3e189-107">`DeviceNetworkInfo` Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о настройке сети для компьютеров, включая сетевые адаптеры, IP-адреса и Mac-адреса, а также подключенные сети или домены.</span><span class="sxs-lookup"><span data-stu-id="3e189-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="3e189-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="3e189-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="3e189-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="3e189-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3e189-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="3e189-110">Column name</span></span> | <span data-ttu-id="3e189-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="3e189-111">Data type</span></span> | <span data-ttu-id="3e189-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3e189-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="3e189-113">datetime</span><span class="sxs-lookup"><span data-stu-id="3e189-113">datetime</span></span> | <span data-ttu-id="3e189-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="3e189-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="3e189-115">string</span><span class="sxs-lookup"><span data-stu-id="3e189-115">string</span></span> | <span data-ttu-id="3e189-116">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="3e189-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="3e189-117">string</span><span class="sxs-lookup"><span data-stu-id="3e189-117">string</span></span> | <span data-ttu-id="3e189-118">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="3e189-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="3e189-119">long</span><span class="sxs-lookup"><span data-stu-id="3e189-119">long</span></span> | <span data-ttu-id="3e189-120">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="3e189-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="3e189-121">Чтобы определить уникальные события, этот столбец должен использоваться в сочетании со столбцами DeviceName и timestamp</span><span class="sxs-lookup"><span data-stu-id="3e189-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="3e189-122">string</span><span class="sxs-lookup"><span data-stu-id="3e189-122">string</span></span> | <span data-ttu-id="3e189-123">Имя сетевого адаптера</span><span class="sxs-lookup"><span data-stu-id="3e189-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="3e189-124">string</span><span class="sxs-lookup"><span data-stu-id="3e189-124">string</span></span> | <span data-ttu-id="3e189-125">MAC-адрес сетевого адаптера</span><span class="sxs-lookup"><span data-stu-id="3e189-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="3e189-126">string</span><span class="sxs-lookup"><span data-stu-id="3e189-126">string</span></span> | <span data-ttu-id="3e189-127">Тип сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="3e189-127">Network adapter type.</span></span> <span data-ttu-id="3e189-128">Чтобы получить возможные значения, обратитесь к [этому перечислению](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="3e189-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="3e189-129">string</span><span class="sxs-lookup"><span data-stu-id="3e189-129">string</span></span> | <span data-ttu-id="3e189-130">Рабочее состояние сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="3e189-130">Operational status of the network adapter.</span></span> <span data-ttu-id="3e189-131">Чтобы получить возможные значения, обратитесь к [этому перечислению](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="3e189-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="3e189-132">string</span><span class="sxs-lookup"><span data-stu-id="3e189-132">string</span></span> | <span data-ttu-id="3e189-133">Туннельный протокол, если для этой цели используется интерфейс, например 6to4, Teredo, ISATAP, PPTP, SSTP и SSH</span><span class="sxs-lookup"><span data-stu-id="3e189-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="3e189-134">string</span><span class="sxs-lookup"><span data-stu-id="3e189-134">string</span></span> | <span data-ttu-id="3e189-135">Сети, к которым подключен адаптер.</span><span class="sxs-lookup"><span data-stu-id="3e189-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="3e189-136">Каждый массив JSON содержит имя сети, категорию (общедоступное, частное, частное или доменное), описание и флаг, указывающий, подключен ли он к Интернету общедоступным</span><span class="sxs-lookup"><span data-stu-id="3e189-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="3e189-137">string</span><span class="sxs-lookup"><span data-stu-id="3e189-137">string</span></span> | <span data-ttu-id="3e189-138">Адреса DNS-серверов в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="3e189-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="3e189-139">string</span><span class="sxs-lookup"><span data-stu-id="3e189-139">string</span></span> | <span data-ttu-id="3e189-140">IPv4-адрес DHCP-сервера</span><span class="sxs-lookup"><span data-stu-id="3e189-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="3e189-141">string</span><span class="sxs-lookup"><span data-stu-id="3e189-141">string</span></span> | <span data-ttu-id="3e189-142">IPv6-адрес DHCP-сервера</span><span class="sxs-lookup"><span data-stu-id="3e189-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="3e189-143">string</span><span class="sxs-lookup"><span data-stu-id="3e189-143">string</span></span> | <span data-ttu-id="3e189-144">Адреса шлюза по умолчанию в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="3e189-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="3e189-145">string</span><span class="sxs-lookup"><span data-stu-id="3e189-145">string</span></span> | <span data-ttu-id="3e189-146">Массив JSON, содержащий все IP-адреса, назначенные адаптеру вместе с соответствующими префиксом и пространством IP-адресов, например общедоступной, частной или локальной локальной связью.</span><span class="sxs-lookup"><span data-stu-id="3e189-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3e189-147">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3e189-147">Related topics</span></span>
- [<span data-ttu-id="3e189-148">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="3e189-148">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3e189-149">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="3e189-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3e189-150">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="3e189-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3e189-151">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="3e189-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3e189-152">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="3e189-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3e189-153">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="3e189-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
