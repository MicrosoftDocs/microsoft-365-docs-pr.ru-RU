---
title: Таблица DeviceTvmSoftwareVulnerabilitiesKB в схеме расширенного поиска
description: Узнайте об уязвимостях программного обеспечения, отслеживаемых средством контроля угроз и уязвимостей, в таблице DeviceTvmSoftwareVulnerabilitiesKB схемы расширенного поиска.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema, reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: afcd6bcd81e1a8635be9ced766c533ea4195334f
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023801"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="705ec-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="705ec-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="705ec-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="705ec-105">**Applies to:**</span></span>
- <span data-ttu-id="705ec-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="705ec-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="705ec-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="705ec-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="705ec-108">Таблица `DeviceTvmSoftwareVulnerabilitiesKB` в схеме расширенного поиска содержит список уязвимостей, на наличие которых [средство контроля угроз и уязвимостей](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) оценивает устройства.</span><span class="sxs-lookup"><span data-stu-id="705ec-108">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="705ec-109">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="705ec-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="705ec-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="705ec-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="705ec-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="705ec-111">Column name</span></span> | <span data-ttu-id="705ec-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="705ec-112">Data type</span></span> | <span data-ttu-id="705ec-113">Описание</span><span class="sxs-lookup"><span data-stu-id="705ec-113">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="705ec-114">string</span><span class="sxs-lookup"><span data-stu-id="705ec-114">string</span></span> | <span data-ttu-id="705ec-115">Уникальный идентификатор, назначенный уязвимости в системе общеизвестных уязвимостей и рисков (CVE)</span><span class="sxs-lookup"><span data-stu-id="705ec-115">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="705ec-116">string</span><span class="sxs-lookup"><span data-stu-id="705ec-116">string</span></span> | <span data-ttu-id="705ec-117">Оценка серьезности, назначенная уязвимости в общей системе оценки уязвимостей (CVSS)</span><span class="sxs-lookup"><span data-stu-id="705ec-117">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="705ec-118">boolean</span><span class="sxs-lookup"><span data-stu-id="705ec-118">boolean</span></span> | <span data-ttu-id="705ec-119">Указывает, является ли общедоступным код эксплойта для уязвимости</span><span class="sxs-lookup"><span data-stu-id="705ec-119">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="705ec-120">string</span><span class="sxs-lookup"><span data-stu-id="705ec-120">string</span></span> | <span data-ttu-id="705ec-121">Уровень серьезности, назначенный уязвимости на основании оценки CVSS и динамических коэффициентов, на которые влияет картина угроз</span><span class="sxs-lookup"><span data-stu-id="705ec-121">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="705ec-122">datetime</span><span class="sxs-lookup"><span data-stu-id="705ec-122">datetime</span></span> | <span data-ttu-id="705ec-123">Дата и время последнего изменения элемента или связанных метаданных</span><span class="sxs-lookup"><span data-stu-id="705ec-123">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="705ec-124">datetime</span><span class="sxs-lookup"><span data-stu-id="705ec-124">datetime</span></span> | <span data-ttu-id="705ec-125">Дата, когда уязвимость была раскрыта для общественности</span><span class="sxs-lookup"><span data-stu-id="705ec-125">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="705ec-126">string</span><span class="sxs-lookup"><span data-stu-id="705ec-126">string</span></span> | <span data-ttu-id="705ec-127">Описание уязвимостей и связанных рисков</span><span class="sxs-lookup"><span data-stu-id="705ec-127">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="705ec-128">string</span><span class="sxs-lookup"><span data-stu-id="705ec-128">string</span></span> | <span data-ttu-id="705ec-129">Список всех программных продуктов, на которые влияет уязвимость</span><span class="sxs-lookup"><span data-stu-id="705ec-129">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="705ec-130">См. также</span><span class="sxs-lookup"><span data-stu-id="705ec-130">Related topics</span></span>

- [<span data-ttu-id="705ec-131">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="705ec-131">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="705ec-132">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="705ec-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="705ec-133">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="705ec-133">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="705ec-134">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="705ec-134">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="705ec-135">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="705ec-135">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="705ec-136">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="705ec-136">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="705ec-137">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="705ec-137">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)