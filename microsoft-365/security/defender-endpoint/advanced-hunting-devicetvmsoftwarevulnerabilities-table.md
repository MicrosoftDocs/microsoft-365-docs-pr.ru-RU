---
title: Таблица DeviceTvmSoftwareVulnerabilities в продвинутой схеме охоты
description: Узнайте об уязвимостях программного обеспечения, найденных на устройствах, и списке доступных обновлений безопасности, которые будут рассматривать каждую уязвимость в таблице DeviceTvmSoftwareVulnerabilities продвинутой схемы охоты.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 6b38297cd0fa2e931619ff9c0557d2ae868c7aa4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076037"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="08b69-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="08b69-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="08b69-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="08b69-105">**Applies to:**</span></span>
- [<span data-ttu-id="08b69-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="08b69-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="08b69-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="08b69-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="08b69-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="08b69-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="08b69-109">Таблица в продвинутой схеме охоты содержит список уязвимостей управления & уязвимостей в `DeviceTvmSoftwareVulnerabilities` установленных программных [](next-gen-threat-and-vuln-mgt.md) продуктах.</span><span class="sxs-lookup"><span data-stu-id="08b69-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="08b69-110">Эта таблица также содержит сведения об операционной системе, ИД CVE и сведения о серьезности уязвимости.</span><span class="sxs-lookup"><span data-stu-id="08b69-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="08b69-111">Например, эту таблицу можно использовать для охоты на события, связанные с устройствами с серьезными уязвимостями в программном обеспечении.</span><span class="sxs-lookup"><span data-stu-id="08b69-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="08b69-112">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="08b69-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="08b69-113">Таблицы `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` и таблицы заменили `DeviceTvmSoftwareInventoryVulnerabilities` таблицу.</span><span class="sxs-lookup"><span data-stu-id="08b69-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="08b69-114">В первых двух таблицах содержится больше столбцов, которые можно использовать для информирования о действиях по управлению уязвимостями.</span><span class="sxs-lookup"><span data-stu-id="08b69-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="08b69-115">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="08b69-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="08b69-116">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="08b69-116">Column name</span></span> | <span data-ttu-id="08b69-117">Тип данных</span><span class="sxs-lookup"><span data-stu-id="08b69-117">Data type</span></span> | <span data-ttu-id="08b69-118">Описание</span><span class="sxs-lookup"><span data-stu-id="08b69-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="08b69-119">string</span><span class="sxs-lookup"><span data-stu-id="08b69-119">string</span></span> | <span data-ttu-id="08b69-120">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="08b69-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="08b69-121">строка</span><span class="sxs-lookup"><span data-stu-id="08b69-121">string</span></span> | <span data-ttu-id="08b69-122">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="08b69-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="08b69-123">строка</span><span class="sxs-lookup"><span data-stu-id="08b69-123">string</span></span> | <span data-ttu-id="08b69-124">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="08b69-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="08b69-125">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="08b69-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="08b69-126">string</span><span class="sxs-lookup"><span data-stu-id="08b69-126">string</span></span> | <span data-ttu-id="08b69-127">Версия операционной системы, запущенной на устройстве</span><span class="sxs-lookup"><span data-stu-id="08b69-127">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="08b69-128">строка</span><span class="sxs-lookup"><span data-stu-id="08b69-128">string</span></span> | <span data-ttu-id="08b69-129">Архитектура операционной системы, запущенной на устройстве</span><span class="sxs-lookup"><span data-stu-id="08b69-129">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="08b69-130">строка</span><span class="sxs-lookup"><span data-stu-id="08b69-130">string</span></span> | <span data-ttu-id="08b69-131">Имя поставщика программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="08b69-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="08b69-132">string</span><span class="sxs-lookup"><span data-stu-id="08b69-132">string</span></span> | <span data-ttu-id="08b69-133">Название программного продукта</span><span class="sxs-lookup"><span data-stu-id="08b69-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="08b69-134">string</span><span class="sxs-lookup"><span data-stu-id="08b69-134">string</span></span> | <span data-ttu-id="08b69-135">Номер версии программного продукта</span><span class="sxs-lookup"><span data-stu-id="08b69-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="08b69-136">string</span><span class="sxs-lookup"><span data-stu-id="08b69-136">string</span></span> | <span data-ttu-id="08b69-137">Уникальный идентификатор, назначенный уязвимости в системе общеизвестных уязвимостей и рисков (CVE)</span><span class="sxs-lookup"><span data-stu-id="08b69-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="08b69-138">string</span><span class="sxs-lookup"><span data-stu-id="08b69-138">string</span></span> | <span data-ttu-id="08b69-139">Уровень серьезности, назначенный уязвимости безопасности на основе оценки CVSS и динамических коэффициентов, на которые влияет обстановка с угрозами</span><span class="sxs-lookup"><span data-stu-id="08b69-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="08b69-140">string</span><span class="sxs-lookup"><span data-stu-id="08b69-140">string</span></span> | <span data-ttu-id="08b69-141">Имя или описание обновления безопасности, предоставляемого поставщиком программного обеспечения для устранения уязвимости</span><span class="sxs-lookup"><span data-stu-id="08b69-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="08b69-142">строка</span><span class="sxs-lookup"><span data-stu-id="08b69-142">string</span></span> | <span data-ttu-id="08b69-143">Идентификатор применимых обновлений или идентификаторов безопасности для соответствующих статей руководства или базы знаний (KB).</span><span class="sxs-lookup"><span data-stu-id="08b69-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="08b69-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="08b69-144">Related topics</span></span>

- [<span data-ttu-id="08b69-145">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="08b69-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="08b69-146">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="08b69-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="08b69-147">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="08b69-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="08b69-148">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="08b69-148">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
