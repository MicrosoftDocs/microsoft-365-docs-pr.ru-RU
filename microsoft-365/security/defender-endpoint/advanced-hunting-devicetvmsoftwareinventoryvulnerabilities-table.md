---
title: Таблица DeviceTvmSoftwareInventoryVulnerabilities в схеме расширенной охоты
description: Сведения об инвентаризации программ на устройствах и их уязвимостях в таблице DeviceTvmSoftwareInventoryVulnerabilities схемы расширенной охоты.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: bbb535aa3f106c8569edb3c64ba95bba9bf36186
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163463"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="275a9-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="275a9-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="275a9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="275a9-105">**Applies to:**</span></span>

- [<span data-ttu-id="275a9-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="275a9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="275a9-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="275a9-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="275a9-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="275a9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="275a9-109">Таблица `DeviceTvmSoftwareInventoryVulnerabilities` схемы расширенной охоты содержит инвентаризацию программ на ваших устройствах с использованием функции [Контроль угроз и уязвимостей](next-gen-threat-and-vuln-mgt.md), а также все известные уязвимости в этих программных продуктах.</span><span class="sxs-lookup"><span data-stu-id="275a9-109">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="275a9-110">Эта таблица также содержит сведения об операционной системе, ИД CVE и сведения о серьезности уязвимости.</span><span class="sxs-lookup"><span data-stu-id="275a9-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="275a9-111">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="275a9-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="275a9-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="275a9-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="275a9-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="275a9-113">Column name</span></span> | <span data-ttu-id="275a9-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="275a9-114">Data type</span></span> | <span data-ttu-id="275a9-115">Описание</span><span class="sxs-lookup"><span data-stu-id="275a9-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="275a9-116">string</span><span class="sxs-lookup"><span data-stu-id="275a9-116">string</span></span> | <span data-ttu-id="275a9-117">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="275a9-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="275a9-118">строка</span><span class="sxs-lookup"><span data-stu-id="275a9-118">string</span></span> | <span data-ttu-id="275a9-119">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="275a9-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="275a9-120">строка</span><span class="sxs-lookup"><span data-stu-id="275a9-120">string</span></span> | <span data-ttu-id="275a9-121">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="275a9-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="275a9-122">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="275a9-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="275a9-123">string</span><span class="sxs-lookup"><span data-stu-id="275a9-123">string</span></span> | <span data-ttu-id="275a9-124">Версия операционной системы, запущенной на устройстве</span><span class="sxs-lookup"><span data-stu-id="275a9-124">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="275a9-125">строка</span><span class="sxs-lookup"><span data-stu-id="275a9-125">string</span></span> | <span data-ttu-id="275a9-126">Архитектура операционной системы, запущенной на устройстве</span><span class="sxs-lookup"><span data-stu-id="275a9-126">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="275a9-127">строка</span><span class="sxs-lookup"><span data-stu-id="275a9-127">string</span></span> | <span data-ttu-id="275a9-128">Имя поставщика программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="275a9-128">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="275a9-129">string</span><span class="sxs-lookup"><span data-stu-id="275a9-129">string</span></span> | <span data-ttu-id="275a9-130">Название программного продукта</span><span class="sxs-lookup"><span data-stu-id="275a9-130">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="275a9-131">string</span><span class="sxs-lookup"><span data-stu-id="275a9-131">string</span></span> | <span data-ttu-id="275a9-132">Номер версии программного продукта</span><span class="sxs-lookup"><span data-stu-id="275a9-132">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="275a9-133">string</span><span class="sxs-lookup"><span data-stu-id="275a9-133">string</span></span> | <span data-ttu-id="275a9-134">Уникальный идентификатор, назначенный уязвимости в системе общеизвестных уязвимостей и рисков (CVE)</span><span class="sxs-lookup"><span data-stu-id="275a9-134">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="275a9-135">string</span><span class="sxs-lookup"><span data-stu-id="275a9-135">string</span></span> | <span data-ttu-id="275a9-136">Уровень серьезности, назначенный уязвимости безопасности на основе оценки CVSS и динамических коэффициентов, на которые влияет обстановка с угрозами</span><span class="sxs-lookup"><span data-stu-id="275a9-136">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="275a9-137">См. также</span><span class="sxs-lookup"><span data-stu-id="275a9-137">Related topics</span></span>

- [<span data-ttu-id="275a9-138">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="275a9-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="275a9-139">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="275a9-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="275a9-140">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="275a9-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="275a9-141">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="275a9-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
