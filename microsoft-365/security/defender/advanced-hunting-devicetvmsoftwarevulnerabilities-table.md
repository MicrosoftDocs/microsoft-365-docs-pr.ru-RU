---
title: Таблица DeviceTvmSoftwareVulnerabilities в продвинутой схеме охоты
description: Узнайте об уязвимостях программного обеспечения, найденных на устройствах, и списке доступных обновлений безопасности, которые будут рассматривать каждую уязвимость в таблице DeviceTvmSoftwareVulnerabilities продвинутой схемы охоты.
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6911031e3caa27eff80bb83a3a88643cac2b6918
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073965"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="c08bf-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="c08bf-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c08bf-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c08bf-105">**Applies to:**</span></span>
- <span data-ttu-id="c08bf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c08bf-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="c08bf-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="c08bf-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c08bf-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="c08bf-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c08bf-109">Таблица в продвинутой схеме охоты содержит список уязвимостей управления & уязвимостей в `DeviceTvmSoftwareVulnerabilities` установленных программных [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) продуктах.</span><span class="sxs-lookup"><span data-stu-id="c08bf-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="c08bf-110">Эта таблица также содержит сведения об операционной системе, ИД CVE и сведения о серьезности уязвимости.</span><span class="sxs-lookup"><span data-stu-id="c08bf-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="c08bf-111">Например, эту таблицу можно использовать для охоты на события, связанные с устройствами с серьезными уязвимостями в программном обеспечении.</span><span class="sxs-lookup"><span data-stu-id="c08bf-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="c08bf-112">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="c08bf-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="c08bf-113">Таблицы `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` и таблицы заменили `DeviceTvmSoftwareInventoryVulnerabilities` таблицу.</span><span class="sxs-lookup"><span data-stu-id="c08bf-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="c08bf-114">В первых двух таблицах содержится больше столбцов, которые можно использовать для информирования о действиях по управлению уязвимыми группами или для охоты за уязвимыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="c08bf-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="c08bf-115">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c08bf-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c08bf-116">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="c08bf-116">Column name</span></span> | <span data-ttu-id="c08bf-117">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c08bf-117">Data type</span></span> | <span data-ttu-id="c08bf-118">Описание</span><span class="sxs-lookup"><span data-stu-id="c08bf-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="c08bf-119">string</span><span class="sxs-lookup"><span data-stu-id="c08bf-119">string</span></span> | <span data-ttu-id="c08bf-120">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="c08bf-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c08bf-121">string</span><span class="sxs-lookup"><span data-stu-id="c08bf-121">string</span></span> | <span data-ttu-id="c08bf-122">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="c08bf-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="c08bf-123">string</span><span class="sxs-lookup"><span data-stu-id="c08bf-123">string</span></span> | <span data-ttu-id="c08bf-124">Платформа операционной системы, используемой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c08bf-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="c08bf-125">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="c08bf-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="c08bf-126">string</span><span class="sxs-lookup"><span data-stu-id="c08bf-126">string</span></span> | <span data-ttu-id="c08bf-127">Версия операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="c08bf-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="c08bf-128">string</span><span class="sxs-lookup"><span data-stu-id="c08bf-128">string</span></span> | <span data-ttu-id="c08bf-129">Архитектура операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="c08bf-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="c08bf-130">string</span><span class="sxs-lookup"><span data-stu-id="c08bf-130">string</span></span> | <span data-ttu-id="c08bf-131">Имя поставщика программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="c08bf-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="c08bf-132">string</span><span class="sxs-lookup"><span data-stu-id="c08bf-132">string</span></span> | <span data-ttu-id="c08bf-133">Название программного продукта</span><span class="sxs-lookup"><span data-stu-id="c08bf-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="c08bf-134">string</span><span class="sxs-lookup"><span data-stu-id="c08bf-134">string</span></span> | <span data-ttu-id="c08bf-135">Номер версии программного продукта</span><span class="sxs-lookup"><span data-stu-id="c08bf-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="c08bf-136">string</span><span class="sxs-lookup"><span data-stu-id="c08bf-136">string</span></span> | <span data-ttu-id="c08bf-137">Уникальный идентификатор, назначенный уязвимости в системе общеизвестных уязвимостей и рисков (CVE)</span><span class="sxs-lookup"><span data-stu-id="c08bf-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="c08bf-138">string</span><span class="sxs-lookup"><span data-stu-id="c08bf-138">string</span></span> | <span data-ttu-id="c08bf-139">Уровень серьезности, назначенный уязвимости безопасности на основе оценки CVSS и динамических коэффициентов, на которые влияет обстановка с угрозами</span><span class="sxs-lookup"><span data-stu-id="c08bf-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="c08bf-140">string</span><span class="sxs-lookup"><span data-stu-id="c08bf-140">string</span></span> | <span data-ttu-id="c08bf-141">Имя или описание обновления безопасности, предоставляемого поставщиком программного обеспечения для устранения уязвимости</span><span class="sxs-lookup"><span data-stu-id="c08bf-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="c08bf-142">строка</span><span class="sxs-lookup"><span data-stu-id="c08bf-142">string</span></span> | <span data-ttu-id="c08bf-143">Идентификатор применимых обновлений или идентификаторов безопасности для соответствующих статей руководства или базы знаний (KB).</span><span class="sxs-lookup"><span data-stu-id="c08bf-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="c08bf-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c08bf-144">Related topics</span></span>

- [<span data-ttu-id="c08bf-145">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="c08bf-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c08bf-146">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="c08bf-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c08bf-147">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="c08bf-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c08bf-148">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="c08bf-148">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c08bf-149">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="c08bf-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c08bf-150">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="c08bf-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c08bf-151">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="c08bf-151">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)