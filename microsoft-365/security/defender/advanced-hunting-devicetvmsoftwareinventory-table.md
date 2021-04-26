---
title: DeviceTvmSoftwareInventory table in the advanced hunting schema
description: Узнайте о инвентаризации программного обеспечения на устройствах в таблице DeviceTvmSoftwareInventory продвинутой схемы охоты.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 5f82684ebb10b72ff83a6789c010f5ec9fa099e7
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024233"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="b53c1-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="b53c1-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b53c1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b53c1-105">**Applies to:**</span></span>
- <span data-ttu-id="b53c1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b53c1-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="b53c1-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b53c1-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="b53c1-108">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="b53c1-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b53c1-109">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="b53c1-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="b53c1-110">Таблица в продвинутой схеме охоты содержит инвентаризацию программного обеспечения управления & уязвимостей, установленного в настоящее время на устройствах в вашей сети, включая конечные сведения `DeviceTvmSoftwareInventory` о поддержке. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="b53c1-110">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="b53c1-111">Например, можно искать события, связанные с устройствами, установленными с уязвимой в настоящее время версией программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="b53c1-111">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="b53c1-112">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="b53c1-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="b53c1-113">Таблицы `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` и таблицы заменили `DeviceTvmSoftwareInventoryVulnerabilities` таблицу.</span><span class="sxs-lookup"><span data-stu-id="b53c1-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="b53c1-114">В первых двух таблицах содержится больше столбцов, которые можно использовать для информирования о действиях по управлению уязвимыми группами или для охоты за уязвимыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="b53c1-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="b53c1-115">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b53c1-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b53c1-116">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="b53c1-116">Column name</span></span> | <span data-ttu-id="b53c1-117">Тип данных</span><span class="sxs-lookup"><span data-stu-id="b53c1-117">Data type</span></span> | <span data-ttu-id="b53c1-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b53c1-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="b53c1-119">string</span><span class="sxs-lookup"><span data-stu-id="b53c1-119">string</span></span> | <span data-ttu-id="b53c1-120">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="b53c1-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b53c1-121">string</span><span class="sxs-lookup"><span data-stu-id="b53c1-121">string</span></span> | <span data-ttu-id="b53c1-122">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="b53c1-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="b53c1-123">string</span><span class="sxs-lookup"><span data-stu-id="b53c1-123">string</span></span> | <span data-ttu-id="b53c1-124">Платформа операционной системы, используемой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b53c1-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="b53c1-125">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b53c1-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="b53c1-126">string</span><span class="sxs-lookup"><span data-stu-id="b53c1-126">string</span></span> | <span data-ttu-id="b53c1-127">Версия операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="b53c1-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="b53c1-128">string</span><span class="sxs-lookup"><span data-stu-id="b53c1-128">string</span></span> | <span data-ttu-id="b53c1-129">Архитектура операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="b53c1-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="b53c1-130">string</span><span class="sxs-lookup"><span data-stu-id="b53c1-130">string</span></span> | <span data-ttu-id="b53c1-131">Имя поставщика программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b53c1-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="b53c1-132">string</span><span class="sxs-lookup"><span data-stu-id="b53c1-132">string</span></span> | <span data-ttu-id="b53c1-133">Название программного продукта</span><span class="sxs-lookup"><span data-stu-id="b53c1-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="b53c1-134">string</span><span class="sxs-lookup"><span data-stu-id="b53c1-134">string</span></span> | <span data-ttu-id="b53c1-135">Номер версии программного продукта</span><span class="sxs-lookup"><span data-stu-id="b53c1-135">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="b53c1-136">string</span><span class="sxs-lookup"><span data-stu-id="b53c1-136">string</span></span> | <span data-ttu-id="b53c1-137">Указывает этап жизненного цикла программного продукта относительно указанной даты окончания поддержки (EOS) или даты окончания срока службы (EOL).</span><span class="sxs-lookup"><span data-stu-id="b53c1-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="b53c1-138">String</span><span class="sxs-lookup"><span data-stu-id="b53c1-138">string</span></span> | <span data-ttu-id="b53c1-139">Дата окончания службы поддержки (EOS) или даты окончания срока службы программного продукта</span><span class="sxs-lookup"><span data-stu-id="b53c1-139">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="b53c1-140">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b53c1-140">Related topics</span></span>

- [<span data-ttu-id="b53c1-141">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="b53c1-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b53c1-142">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="b53c1-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b53c1-143">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="b53c1-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b53c1-144">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="b53c1-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b53c1-145">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="b53c1-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b53c1-146">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="b53c1-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b53c1-147">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="b53c1-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)