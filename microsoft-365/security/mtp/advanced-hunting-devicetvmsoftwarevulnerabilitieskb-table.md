---
title: Таблица DeviceTvmSoftwareVulnerabilitiesKB в схеме расширенного поиска
description: Узнайте об уязвимостях программного обеспечения, отслеживаемых средством контроля угроз и уязвимостей, в таблице DeviceTvmSoftwareVulnerabilitiesKB схемы расширенного поиска.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 00474ac13f88cd9a00ea2ba4a53a6e30ddd664c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931054"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="0b7c9-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="0b7c9-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0b7c9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0b7c9-105">**Applies to:**</span></span>
- <span data-ttu-id="0b7c9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b7c9-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="0b7c9-107">Таблица `DeviceTvmSoftwareVulnerabilitiesKB` в схеме расширенного поиска содержит список уязвимостей, на наличие которых [средство контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) оценивает устройства.</span><span class="sxs-lookup"><span data-stu-id="0b7c9-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="0b7c9-108">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="0b7c9-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="0b7c9-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0b7c9-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0b7c9-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="0b7c9-110">Column name</span></span> | <span data-ttu-id="0b7c9-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0b7c9-111">Data type</span></span> | <span data-ttu-id="0b7c9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0b7c9-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="0b7c9-113">string</span><span class="sxs-lookup"><span data-stu-id="0b7c9-113">string</span></span> | <span data-ttu-id="0b7c9-114">Уникальный идентификатор, назначенный уязвимости в системе общеизвестных уязвимостей и рисков (CVE)</span><span class="sxs-lookup"><span data-stu-id="0b7c9-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="0b7c9-115">string</span><span class="sxs-lookup"><span data-stu-id="0b7c9-115">string</span></span> | <span data-ttu-id="0b7c9-116">Оценка серьезности, назначенная уязвимости в общей системе оценки уязвимостей (CVSS)</span><span class="sxs-lookup"><span data-stu-id="0b7c9-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="0b7c9-117">boolean</span><span class="sxs-lookup"><span data-stu-id="0b7c9-117">boolean</span></span> | <span data-ttu-id="0b7c9-118">Указывает, является ли общедоступным код эксплойта для уязвимости</span><span class="sxs-lookup"><span data-stu-id="0b7c9-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="0b7c9-119">string</span><span class="sxs-lookup"><span data-stu-id="0b7c9-119">string</span></span> | <span data-ttu-id="0b7c9-120">Уровень серьезности, назначенный уязвимости на основании оценки CVSS и динамических коэффициентов, на которые влияет картина угроз</span><span class="sxs-lookup"><span data-stu-id="0b7c9-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="0b7c9-121">datetime</span><span class="sxs-lookup"><span data-stu-id="0b7c9-121">datetime</span></span> | <span data-ttu-id="0b7c9-122">Дата и время последнего изменения элемента или связанных метаданных</span><span class="sxs-lookup"><span data-stu-id="0b7c9-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="0b7c9-123">datetime</span><span class="sxs-lookup"><span data-stu-id="0b7c9-123">datetime</span></span> | <span data-ttu-id="0b7c9-124">Дата, когда уязвимость была раскрыта для общественности</span><span class="sxs-lookup"><span data-stu-id="0b7c9-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="0b7c9-125">string</span><span class="sxs-lookup"><span data-stu-id="0b7c9-125">string</span></span> | <span data-ttu-id="0b7c9-126">Описание уязвимостей и связанных рисков</span><span class="sxs-lookup"><span data-stu-id="0b7c9-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="0b7c9-127">string</span><span class="sxs-lookup"><span data-stu-id="0b7c9-127">string</span></span> | <span data-ttu-id="0b7c9-128">Список всех программных продуктов, на которые влияет уязвимость</span><span class="sxs-lookup"><span data-stu-id="0b7c9-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0b7c9-129">См. также</span><span class="sxs-lookup"><span data-stu-id="0b7c9-129">Related topics</span></span>

- [<span data-ttu-id="0b7c9-130">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="0b7c9-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0b7c9-131">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="0b7c9-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0b7c9-132">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="0b7c9-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0b7c9-133">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="0b7c9-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0b7c9-134">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="0b7c9-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0b7c9-135">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="0b7c9-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="0b7c9-136">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="0b7c9-136">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
