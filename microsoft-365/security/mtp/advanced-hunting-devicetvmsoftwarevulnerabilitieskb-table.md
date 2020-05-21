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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 378ffee34a24af225b1b6deebd7cc514c62e1926
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "44328002"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="c218c-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="c218c-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

<span data-ttu-id="c218c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c218c-105">**Applies to:**</span></span>
- <span data-ttu-id="c218c-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c218c-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="c218c-107">Таблица `DeviceTvmSoftwareVulnerabilitiesKB` в схеме расширенного поиска содержит список уязвимостей, на наличие которых [средство контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) оценивает устройства.</span><span class="sxs-lookup"><span data-stu-id="c218c-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="c218c-108">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="c218c-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="c218c-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c218c-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c218c-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="c218c-110">Column name</span></span> | <span data-ttu-id="c218c-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c218c-111">Data type</span></span> | <span data-ttu-id="c218c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c218c-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="c218c-113">string</span><span class="sxs-lookup"><span data-stu-id="c218c-113">string</span></span> | <span data-ttu-id="c218c-114">Уникальный идентификатор, назначенный уязвимости в системе общеизвестных уязвимостей и рисков (CVE)</span><span class="sxs-lookup"><span data-stu-id="c218c-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="c218c-115">string</span><span class="sxs-lookup"><span data-stu-id="c218c-115">string</span></span> | <span data-ttu-id="c218c-116">Оценка серьезности, назначенная уязвимости в общей системе оценки уязвимостей (CVSS)</span><span class="sxs-lookup"><span data-stu-id="c218c-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="c218c-117">boolean</span><span class="sxs-lookup"><span data-stu-id="c218c-117">boolean</span></span> | <span data-ttu-id="c218c-118">Указывает, является ли общедоступным код эксплойта для уязвимости</span><span class="sxs-lookup"><span data-stu-id="c218c-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="c218c-119">string</span><span class="sxs-lookup"><span data-stu-id="c218c-119">string</span></span> | <span data-ttu-id="c218c-120">Уровень серьезности, назначенный уязвимости на основании оценки CVSS и динамических коэффициентов, на которые влияет картина угроз</span><span class="sxs-lookup"><span data-stu-id="c218c-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="c218c-121">datetime</span><span class="sxs-lookup"><span data-stu-id="c218c-121">datetime</span></span> | <span data-ttu-id="c218c-122">Дата и время последнего изменения элемента или связанных метаданных</span><span class="sxs-lookup"><span data-stu-id="c218c-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="c218c-123">datetime</span><span class="sxs-lookup"><span data-stu-id="c218c-123">datetime</span></span> | <span data-ttu-id="c218c-124">Дата, когда уязвимость была раскрыта для общественности</span><span class="sxs-lookup"><span data-stu-id="c218c-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="c218c-125">string</span><span class="sxs-lookup"><span data-stu-id="c218c-125">string</span></span> | <span data-ttu-id="c218c-126">Описание уязвимостей и связанных рисков</span><span class="sxs-lookup"><span data-stu-id="c218c-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="c218c-127">string</span><span class="sxs-lookup"><span data-stu-id="c218c-127">string</span></span> | <span data-ttu-id="c218c-128">Список всех программных продуктов, на которые влияет уязвимость</span><span class="sxs-lookup"><span data-stu-id="c218c-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c218c-129">См. также</span><span class="sxs-lookup"><span data-stu-id="c218c-129">Related topics</span></span>

- [<span data-ttu-id="c218c-130">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="c218c-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c218c-131">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="c218c-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c218c-132">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="c218c-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c218c-133">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="c218c-133">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c218c-134">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="c218c-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c218c-135">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="c218c-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c218c-136">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="c218c-136">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
