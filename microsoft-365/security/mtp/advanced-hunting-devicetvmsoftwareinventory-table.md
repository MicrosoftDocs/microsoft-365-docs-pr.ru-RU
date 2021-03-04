---
title: DeviceTvmSoftwareInventory table in the advanced hunting schema
description: Узнайте о инвентаризации программного обеспечения на устройствах в таблице DeviceTvmSoftwareInventory продвинутой схемы охоты.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 445e6f767cc2269315a0b280df2f4deefa2faa08
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423979"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="126bc-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="126bc-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="126bc-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="126bc-105">**Applies to:**</span></span>
- <span data-ttu-id="126bc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="126bc-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="126bc-107">Некоторые сведения относятся к предварительно изданным продуктам, которые могут быть существенно изменены до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="126bc-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="126bc-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="126bc-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="126bc-109">Таблица в продвинутой схеме охоты содержит инвентаризацию программного обеспечения управления & уязвимостей, установленного в настоящее время на устройствах в вашей сети, включая конечные сведения `DeviceTvmSoftwareInventory` о поддержке. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="126bc-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="126bc-110">Например, можно искать события, связанные с устройствами, установленными с уязвимой в настоящее время версией программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="126bc-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="126bc-111">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="126bc-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="126bc-112">Таблицы `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` и таблицы заменили `DeviceTvmSoftwareInventoryVulnerabilities` таблицу.</span><span class="sxs-lookup"><span data-stu-id="126bc-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="126bc-113">В первых двух таблицах содержится больше столбцов, которые можно использовать для информирования о действиях по управлению уязвимыми группами или для охоты за уязвимыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="126bc-113">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="126bc-114">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="126bc-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="126bc-115">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="126bc-115">Column name</span></span> | <span data-ttu-id="126bc-116">Тип данных</span><span class="sxs-lookup"><span data-stu-id="126bc-116">Data type</span></span> | <span data-ttu-id="126bc-117">Описание</span><span class="sxs-lookup"><span data-stu-id="126bc-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="126bc-118">string</span><span class="sxs-lookup"><span data-stu-id="126bc-118">string</span></span> | <span data-ttu-id="126bc-119">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="126bc-119">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="126bc-120">string</span><span class="sxs-lookup"><span data-stu-id="126bc-120">string</span></span> | <span data-ttu-id="126bc-121">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="126bc-121">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="126bc-122">string</span><span class="sxs-lookup"><span data-stu-id="126bc-122">string</span></span> | <span data-ttu-id="126bc-123">Платформа операционной системы, используемой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="126bc-123">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="126bc-124">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="126bc-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="126bc-125">string</span><span class="sxs-lookup"><span data-stu-id="126bc-125">string</span></span> | <span data-ttu-id="126bc-126">Версия операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="126bc-126">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="126bc-127">string</span><span class="sxs-lookup"><span data-stu-id="126bc-127">string</span></span> | <span data-ttu-id="126bc-128">Архитектура операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="126bc-128">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="126bc-129">string</span><span class="sxs-lookup"><span data-stu-id="126bc-129">string</span></span> | <span data-ttu-id="126bc-130">Имя поставщика программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="126bc-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="126bc-131">string</span><span class="sxs-lookup"><span data-stu-id="126bc-131">string</span></span> | <span data-ttu-id="126bc-132">Название программного продукта</span><span class="sxs-lookup"><span data-stu-id="126bc-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="126bc-133">string</span><span class="sxs-lookup"><span data-stu-id="126bc-133">string</span></span> | <span data-ttu-id="126bc-134">Номер версии программного продукта</span><span class="sxs-lookup"><span data-stu-id="126bc-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="126bc-135">string</span><span class="sxs-lookup"><span data-stu-id="126bc-135">string</span></span> | <span data-ttu-id="126bc-136">Указывает этап жизненного цикла программного продукта относительно указанной даты окончания поддержки (EOS) или даты окончания срока службы (EOL).</span><span class="sxs-lookup"><span data-stu-id="126bc-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="126bc-137">string</span><span class="sxs-lookup"><span data-stu-id="126bc-137">string</span></span> | <span data-ttu-id="126bc-138">Дата окончания службы поддержки (EOS) или даты окончания срока службы программного продукта</span><span class="sxs-lookup"><span data-stu-id="126bc-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="126bc-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="126bc-139">Related topics</span></span>

- [<span data-ttu-id="126bc-140">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="126bc-140">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="126bc-141">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="126bc-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="126bc-142">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="126bc-142">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="126bc-143">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="126bc-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="126bc-144">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="126bc-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="126bc-145">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="126bc-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="126bc-146">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="126bc-146">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
