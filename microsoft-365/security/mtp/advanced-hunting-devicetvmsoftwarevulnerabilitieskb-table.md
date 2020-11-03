---
title: Таблица DeviceTvmSoftwareVulnerabilitiesKB в схеме расширенного поиска
description: Узнайте об уязвимостях программного обеспечения, отслеживаемых средством контроля угроз и уязвимостей, в таблице DeviceTvmSoftwareVulnerabilitiesKB схемы расширенного поиска.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, метрическое содержание, схема, справочные материалы, Кусто, таблица, столбец, тип данных, описание, угроза & уязвимости, ТВМ, Управление устройствами, программное обеспечение, наличие уязвимостей, CVE ID, КВСС, Девицетвмсофтваревулнерабилитиескб
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: f5cbc037dce72979874be6246a24ea3491a90df1
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847492"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="245c5-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="245c5-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="245c5-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="245c5-105">**Applies to:**</span></span>
- <span data-ttu-id="245c5-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="245c5-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="245c5-107">Таблица `DeviceTvmSoftwareVulnerabilitiesKB` в схеме расширенного поиска содержит список уязвимостей, на наличие которых [средство контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) оценивает устройства.</span><span class="sxs-lookup"><span data-stu-id="245c5-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="245c5-108">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="245c5-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="245c5-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="245c5-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="245c5-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="245c5-110">Column name</span></span> | <span data-ttu-id="245c5-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="245c5-111">Data type</span></span> | <span data-ttu-id="245c5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="245c5-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="245c5-113">string</span><span class="sxs-lookup"><span data-stu-id="245c5-113">string</span></span> | <span data-ttu-id="245c5-114">Уникальный идентификатор, назначенный уязвимости в системе общеизвестных уязвимостей и рисков (CVE)</span><span class="sxs-lookup"><span data-stu-id="245c5-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="245c5-115">string</span><span class="sxs-lookup"><span data-stu-id="245c5-115">string</span></span> | <span data-ttu-id="245c5-116">Оценка серьезности, назначенная уязвимости в общей системе оценки уязвимостей (CVSS)</span><span class="sxs-lookup"><span data-stu-id="245c5-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="245c5-117">boolean</span><span class="sxs-lookup"><span data-stu-id="245c5-117">boolean</span></span> | <span data-ttu-id="245c5-118">Указывает, является ли общедоступным код эксплойта для уязвимости</span><span class="sxs-lookup"><span data-stu-id="245c5-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="245c5-119">string</span><span class="sxs-lookup"><span data-stu-id="245c5-119">string</span></span> | <span data-ttu-id="245c5-120">Уровень серьезности, назначенный уязвимости на основании оценки CVSS и динамических коэффициентов, на которые влияет картина угроз</span><span class="sxs-lookup"><span data-stu-id="245c5-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="245c5-121">datetime</span><span class="sxs-lookup"><span data-stu-id="245c5-121">datetime</span></span> | <span data-ttu-id="245c5-122">Дата и время последнего изменения элемента или связанных метаданных</span><span class="sxs-lookup"><span data-stu-id="245c5-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="245c5-123">datetime</span><span class="sxs-lookup"><span data-stu-id="245c5-123">datetime</span></span> | <span data-ttu-id="245c5-124">Дата, когда уязвимость была раскрыта для общественности</span><span class="sxs-lookup"><span data-stu-id="245c5-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="245c5-125">string</span><span class="sxs-lookup"><span data-stu-id="245c5-125">string</span></span> | <span data-ttu-id="245c5-126">Описание уязвимостей и связанных рисков</span><span class="sxs-lookup"><span data-stu-id="245c5-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="245c5-127">string</span><span class="sxs-lookup"><span data-stu-id="245c5-127">string</span></span> | <span data-ttu-id="245c5-128">Список всех программных продуктов, на которые влияет уязвимость</span><span class="sxs-lookup"><span data-stu-id="245c5-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="245c5-129">См. также</span><span class="sxs-lookup"><span data-stu-id="245c5-129">Related topics</span></span>

- [<span data-ttu-id="245c5-130">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="245c5-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="245c5-131">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="245c5-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="245c5-132">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="245c5-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="245c5-133">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="245c5-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="245c5-134">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="245c5-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="245c5-135">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="245c5-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="245c5-136">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="245c5-136">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
