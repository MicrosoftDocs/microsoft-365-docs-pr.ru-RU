---
title: Таблица DeviceTvmSoftwareVulnerabilitiesKB в схеме расширенного поиска
description: Узнайте об уязвимостях программного обеспечения, отслеживаемых средством контроля угроз и уязвимостей, в таблице DeviceTvmSoftwareVulnerabilitiesKB схемы расширенного поиска.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 772a287097f0b204eb329d066cdd81c4eef7a755
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070925"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="f4b81-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="f4b81-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f4b81-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f4b81-105">**Applies to:**</span></span>
- [<span data-ttu-id="f4b81-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f4b81-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="f4b81-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f4b81-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f4b81-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f4b81-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f4b81-109">Таблица `DeviceTvmSoftwareVulnerabilitiesKB` в схеме расширенного поиска содержит список уязвимостей, на наличие которых [средство контроля угроз и уязвимостей](next-gen-threat-and-vuln-mgt.md) оценивает устройства.</span><span class="sxs-lookup"><span data-stu-id="f4b81-109">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) assesses devices for.</span></span> <span data-ttu-id="f4b81-110">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="f4b81-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="f4b81-111">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="f4b81-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="f4b81-112">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="f4b81-112">Column name</span></span> | <span data-ttu-id="f4b81-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f4b81-113">Data type</span></span> | <span data-ttu-id="f4b81-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f4b81-114">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="f4b81-115">string</span><span class="sxs-lookup"><span data-stu-id="f4b81-115">string</span></span> | <span data-ttu-id="f4b81-116">Уникальный идентификатор, назначенный уязвимости в системе общеизвестных уязвимостей и рисков (CVE)</span><span class="sxs-lookup"><span data-stu-id="f4b81-116">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="f4b81-117">string</span><span class="sxs-lookup"><span data-stu-id="f4b81-117">string</span></span> | <span data-ttu-id="f4b81-118">Оценка серьезности, назначенная уязвимости в общей системе оценки уязвимостей (CVSS)</span><span class="sxs-lookup"><span data-stu-id="f4b81-118">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="f4b81-119">boolean</span><span class="sxs-lookup"><span data-stu-id="f4b81-119">boolean</span></span> | <span data-ttu-id="f4b81-120">Указывает, является ли общедоступным код эксплойта для уязвимости</span><span class="sxs-lookup"><span data-stu-id="f4b81-120">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="f4b81-121">string</span><span class="sxs-lookup"><span data-stu-id="f4b81-121">string</span></span> | <span data-ttu-id="f4b81-122">Уровень серьезности, назначенный уязвимости на основании оценки CVSS и динамических коэффициентов, на которые влияет картина угроз</span><span class="sxs-lookup"><span data-stu-id="f4b81-122">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="f4b81-123">datetime</span><span class="sxs-lookup"><span data-stu-id="f4b81-123">datetime</span></span> | <span data-ttu-id="f4b81-124">Дата и время последнего изменения элемента или связанных метаданных</span><span class="sxs-lookup"><span data-stu-id="f4b81-124">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="f4b81-125">datetime</span><span class="sxs-lookup"><span data-stu-id="f4b81-125">datetime</span></span> | <span data-ttu-id="f4b81-126">Дата, когда уязвимость была раскрыта для общественности</span><span class="sxs-lookup"><span data-stu-id="f4b81-126">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="f4b81-127">string</span><span class="sxs-lookup"><span data-stu-id="f4b81-127">string</span></span> | <span data-ttu-id="f4b81-128">Описание уязвимостей и связанных рисков</span><span class="sxs-lookup"><span data-stu-id="f4b81-128">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="f4b81-129">string</span><span class="sxs-lookup"><span data-stu-id="f4b81-129">string</span></span> | <span data-ttu-id="f4b81-130">Список всех программных продуктов, на которые влияет уязвимость</span><span class="sxs-lookup"><span data-stu-id="f4b81-130">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f4b81-131">См. также</span><span class="sxs-lookup"><span data-stu-id="f4b81-131">Related topics</span></span>

- [<span data-ttu-id="f4b81-132">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="f4b81-132">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f4b81-133">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="f4b81-133">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f4b81-134">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="f4b81-134">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="f4b81-135">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="f4b81-135">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
