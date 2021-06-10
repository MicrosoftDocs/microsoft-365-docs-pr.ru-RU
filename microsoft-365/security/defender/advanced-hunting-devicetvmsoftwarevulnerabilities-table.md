---
title: Таблица DeviceTvmSoftwareVulnerabilities в продвинутой схеме охоты
description: Узнайте об уязвимостях программного обеспечения, найденных на устройствах, и списке доступных обновлений безопасности, которые будут рассматривать каждую уязвимость в таблице DeviceTvmSoftwareVulnerabilities продвинутой схемы охоты.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & управление уязвимостями, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 17faffc45cfd1f472dec3f423681aaa3f64944a3
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023813"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="4a708-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="4a708-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4a708-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4a708-105">**Applies to:**</span></span>
- <span data-ttu-id="4a708-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a708-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="4a708-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4a708-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="4a708-108">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="4a708-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="4a708-109">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="4a708-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="4a708-110">Таблица в продвинутой схеме охоты содержит список уязвимостей управления & уязвимостей в `DeviceTvmSoftwareVulnerabilities` установленных программных [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) продуктах.</span><span class="sxs-lookup"><span data-stu-id="4a708-110">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="4a708-111">Эта таблица также содержит сведения об операционной системе, ИД CVE и сведения о серьезности уязвимости.</span><span class="sxs-lookup"><span data-stu-id="4a708-111">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="4a708-112">Например, эту таблицу можно использовать для охоты на события, связанные с устройствами с серьезными уязвимостями в программном обеспечении.</span><span class="sxs-lookup"><span data-stu-id="4a708-112">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="4a708-113">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="4a708-113">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="4a708-114">Таблицы `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` и таблицы заменили `DeviceTvmSoftwareInventoryVulnerabilities` таблицу.</span><span class="sxs-lookup"><span data-stu-id="4a708-114">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="4a708-115">В первых двух таблицах содержится больше столбцов, которые можно использовать для информирования о действиях по управлению уязвимыми группами или для охоты за уязвимыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="4a708-115">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="4a708-116">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="4a708-116">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4a708-117">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="4a708-117">Column name</span></span> | <span data-ttu-id="4a708-118">Тип данных</span><span class="sxs-lookup"><span data-stu-id="4a708-118">Data type</span></span> | <span data-ttu-id="4a708-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4a708-119">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="4a708-120">string</span><span class="sxs-lookup"><span data-stu-id="4a708-120">string</span></span> | <span data-ttu-id="4a708-121">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="4a708-121">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="4a708-122">string</span><span class="sxs-lookup"><span data-stu-id="4a708-122">string</span></span> | <span data-ttu-id="4a708-123">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="4a708-123">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="4a708-124">string</span><span class="sxs-lookup"><span data-stu-id="4a708-124">string</span></span> | <span data-ttu-id="4a708-125">Платформа операционной системы, используемой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4a708-125">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="4a708-126">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="4a708-126">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="4a708-127">string</span><span class="sxs-lookup"><span data-stu-id="4a708-127">string</span></span> | <span data-ttu-id="4a708-128">Версия операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="4a708-128">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="4a708-129">string</span><span class="sxs-lookup"><span data-stu-id="4a708-129">string</span></span> | <span data-ttu-id="4a708-130">Архитектура операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="4a708-130">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="4a708-131">string</span><span class="sxs-lookup"><span data-stu-id="4a708-131">string</span></span> | <span data-ttu-id="4a708-132">Имя поставщика программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="4a708-132">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="4a708-133">string</span><span class="sxs-lookup"><span data-stu-id="4a708-133">string</span></span> | <span data-ttu-id="4a708-134">Название программного продукта</span><span class="sxs-lookup"><span data-stu-id="4a708-134">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="4a708-135">string</span><span class="sxs-lookup"><span data-stu-id="4a708-135">string</span></span> | <span data-ttu-id="4a708-136">Номер версии программного продукта</span><span class="sxs-lookup"><span data-stu-id="4a708-136">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="4a708-137">string</span><span class="sxs-lookup"><span data-stu-id="4a708-137">string</span></span> | <span data-ttu-id="4a708-138">Уникальный идентификатор, назначенный уязвимости в системе общеизвестных уязвимостей и рисков (CVE)</span><span class="sxs-lookup"><span data-stu-id="4a708-138">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="4a708-139">string</span><span class="sxs-lookup"><span data-stu-id="4a708-139">string</span></span> | <span data-ttu-id="4a708-140">Уровень серьезности, назначенный уязвимости безопасности на основе оценки CVSS и динамических коэффициентов, на которые влияет обстановка с угрозами</span><span class="sxs-lookup"><span data-stu-id="4a708-140">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="4a708-141">string</span><span class="sxs-lookup"><span data-stu-id="4a708-141">string</span></span> | <span data-ttu-id="4a708-142">Имя или описание обновления безопасности, предоставляемого поставщиком программного обеспечения для устранения уязвимости</span><span class="sxs-lookup"><span data-stu-id="4a708-142">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="4a708-143">Строка</span><span class="sxs-lookup"><span data-stu-id="4a708-143">string</span></span> | <span data-ttu-id="4a708-144">Идентификатор применимых обновлений или идентификаторов безопасности для соответствующих статей руководства или базы знаний (KB).</span><span class="sxs-lookup"><span data-stu-id="4a708-144">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="4a708-145">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4a708-145">Related topics</span></span>

- [<span data-ttu-id="4a708-146">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="4a708-146">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4a708-147">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="4a708-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4a708-148">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="4a708-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4a708-149">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="4a708-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4a708-150">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="4a708-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4a708-151">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="4a708-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="4a708-152">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="4a708-152">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)