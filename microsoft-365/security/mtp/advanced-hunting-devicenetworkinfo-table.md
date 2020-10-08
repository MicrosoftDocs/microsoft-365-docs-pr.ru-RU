---
title: Таблица девиценетворкинфо в схеме расширенного поискового окна
description: Сведения о конфигурации сети в таблице Девиценетворкинфо расширенной схемы подсистемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрия, справочные материалы, Кусто, таблица, столбец, тип данных, описание, мачиненетворкинфо, Девиценетворкинфо, устройство, компьютер, Mac, IP-адрес, адаптер, DNS, шлюз, туннель
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
ms.openlocfilehash: b874ef77dcf6efacd7adeff18553c0c8e6752bda
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197077"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="5fc57-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="5fc57-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5fc57-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5fc57-105">**Applies to:**</span></span>
- <span data-ttu-id="5fc57-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="5fc57-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="5fc57-107">`DeviceNetworkInfo`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о настройке сети для компьютеров, включая сетевые адаптеры, IP-адреса и Mac-адреса, а также подключенные сети или домены.</span><span class="sxs-lookup"><span data-stu-id="5fc57-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="5fc57-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="5fc57-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="5fc57-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="5fc57-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5fc57-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="5fc57-110">Column name</span></span> | <span data-ttu-id="5fc57-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="5fc57-111">Data type</span></span> | <span data-ttu-id="5fc57-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5fc57-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5fc57-113">datetime</span><span class="sxs-lookup"><span data-stu-id="5fc57-113">datetime</span></span> | <span data-ttu-id="5fc57-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="5fc57-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="5fc57-115">string</span><span class="sxs-lookup"><span data-stu-id="5fc57-115">string</span></span> | <span data-ttu-id="5fc57-116">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="5fc57-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5fc57-117">string</span><span class="sxs-lookup"><span data-stu-id="5fc57-117">string</span></span> | <span data-ttu-id="5fc57-118">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="5fc57-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="5fc57-119">long</span><span class="sxs-lookup"><span data-stu-id="5fc57-119">long</span></span> | <span data-ttu-id="5fc57-120">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="5fc57-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="5fc57-121">Чтобы определить уникальные события, этот столбец должен использоваться в сочетании со столбцами DeviceName и timestamp</span><span class="sxs-lookup"><span data-stu-id="5fc57-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="5fc57-122">string</span><span class="sxs-lookup"><span data-stu-id="5fc57-122">string</span></span> | <span data-ttu-id="5fc57-123">Имя сетевого адаптера</span><span class="sxs-lookup"><span data-stu-id="5fc57-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="5fc57-124">string</span><span class="sxs-lookup"><span data-stu-id="5fc57-124">string</span></span> | <span data-ttu-id="5fc57-125">MAC-адрес сетевого адаптера</span><span class="sxs-lookup"><span data-stu-id="5fc57-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="5fc57-126">string</span><span class="sxs-lookup"><span data-stu-id="5fc57-126">string</span></span> | <span data-ttu-id="5fc57-127">Тип сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="5fc57-127">Network adapter type.</span></span> <span data-ttu-id="5fc57-128">Чтобы получить возможные значения, обратитесь к [этому перечислению](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="5fc57-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="5fc57-129">string</span><span class="sxs-lookup"><span data-stu-id="5fc57-129">string</span></span> | <span data-ttu-id="5fc57-130">Рабочее состояние сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="5fc57-130">Operational status of the network adapter.</span></span> <span data-ttu-id="5fc57-131">Чтобы получить возможные значения, обратитесь к [этому перечислению](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="5fc57-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="5fc57-132">string</span><span class="sxs-lookup"><span data-stu-id="5fc57-132">string</span></span> | <span data-ttu-id="5fc57-133">Туннельный протокол, если для этой цели используется интерфейс, например 6to4, Teredo, ISATAP, PPTP, SSTP и SSH</span><span class="sxs-lookup"><span data-stu-id="5fc57-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="5fc57-134">string</span><span class="sxs-lookup"><span data-stu-id="5fc57-134">string</span></span> | <span data-ttu-id="5fc57-135">Сети, к которым подключен адаптер.</span><span class="sxs-lookup"><span data-stu-id="5fc57-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="5fc57-136">Каждый массив JSON содержит имя сети, категорию (общедоступное, частное, частное или доменное), описание и флаг, указывающий, подключен ли он к Интернету общедоступным</span><span class="sxs-lookup"><span data-stu-id="5fc57-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="5fc57-137">string</span><span class="sxs-lookup"><span data-stu-id="5fc57-137">string</span></span> | <span data-ttu-id="5fc57-138">Адреса DNS-серверов в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="5fc57-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="5fc57-139">string</span><span class="sxs-lookup"><span data-stu-id="5fc57-139">string</span></span> | <span data-ttu-id="5fc57-140">IPv4-адрес DHCP-сервера</span><span class="sxs-lookup"><span data-stu-id="5fc57-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="5fc57-141">string</span><span class="sxs-lookup"><span data-stu-id="5fc57-141">string</span></span> | <span data-ttu-id="5fc57-142">IPv6-адрес DHCP-сервера</span><span class="sxs-lookup"><span data-stu-id="5fc57-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="5fc57-143">string</span><span class="sxs-lookup"><span data-stu-id="5fc57-143">string</span></span> | <span data-ttu-id="5fc57-144">Адреса шлюза по умолчанию в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="5fc57-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="5fc57-145">string</span><span class="sxs-lookup"><span data-stu-id="5fc57-145">string</span></span> | <span data-ttu-id="5fc57-146">Массив JSON, содержащий все IP-адреса, назначенные адаптеру вместе с соответствующими префиксом и пространством IP-адресов, например общедоступной, частной или локальной локальной связью.</span><span class="sxs-lookup"><span data-stu-id="5fc57-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5fc57-147">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="5fc57-147">Related topics</span></span>
- [<span data-ttu-id="5fc57-148">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="5fc57-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5fc57-149">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="5fc57-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5fc57-150">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="5fc57-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5fc57-151">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="5fc57-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5fc57-152">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="5fc57-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5fc57-153">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="5fc57-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
