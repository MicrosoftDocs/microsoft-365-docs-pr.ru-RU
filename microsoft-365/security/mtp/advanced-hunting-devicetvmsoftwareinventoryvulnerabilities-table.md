---
title: Таблица DeviceTvmSoftwareInventoryVulnerabilities в схеме расширенной охоты
description: Сведения об инвентаризации программ на устройствах и их уязвимостях в таблице DeviceTvmSoftwareInventoryVulnerabilities схемы расширенной охоты.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справочник по схемам, Кусто, таблица, столбец, тип данных, описание, угроза & уязвимости, ТВМ, Управление устройствами, программное обеспечение, наличие уязвимостей, CVE ID, OS Девицетвмсофтвареинвенторивулнерабилитиес
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
ms.openlocfilehash: 0a7ac5a68bcdb12b3cdcd94cac8012c7807a6e2b
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327994"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="22cf9-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="22cf9-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

<span data-ttu-id="22cf9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="22cf9-105">**Applies to:**</span></span>
- <span data-ttu-id="22cf9-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="22cf9-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="22cf9-107">Таблица `DeviceTvmSoftwareInventoryVulnerabilities` схемы расширенной охоты содержит инвентаризацию программ на ваших устройствах с использованием функции [Контроль угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt), а также все известные уязвимости в этих программных продуктах.</span><span class="sxs-lookup"><span data-stu-id="22cf9-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="22cf9-108">Эта таблица также содержит сведения об операционной системе, ИД CVE и сведения о серьезности уязвимости.</span><span class="sxs-lookup"><span data-stu-id="22cf9-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="22cf9-109">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="22cf9-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="22cf9-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="22cf9-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="22cf9-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="22cf9-111">Column name</span></span> | <span data-ttu-id="22cf9-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="22cf9-112">Data type</span></span> | <span data-ttu-id="22cf9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="22cf9-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="22cf9-114">string</span><span class="sxs-lookup"><span data-stu-id="22cf9-114">string</span></span> | <span data-ttu-id="22cf9-115">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="22cf9-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="22cf9-116">string</span><span class="sxs-lookup"><span data-stu-id="22cf9-116">string</span></span> | <span data-ttu-id="22cf9-117">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="22cf9-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="22cf9-118">string</span><span class="sxs-lookup"><span data-stu-id="22cf9-118">string</span></span> | <span data-ttu-id="22cf9-119">Платформа операционной системы, используемой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="22cf9-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="22cf9-120">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="22cf9-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="22cf9-121">string</span><span class="sxs-lookup"><span data-stu-id="22cf9-121">string</span></span> | <span data-ttu-id="22cf9-122">Версия операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="22cf9-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="22cf9-123">string</span><span class="sxs-lookup"><span data-stu-id="22cf9-123">string</span></span> | <span data-ttu-id="22cf9-124">Архитектура операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="22cf9-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="22cf9-125">string</span><span class="sxs-lookup"><span data-stu-id="22cf9-125">string</span></span> | <span data-ttu-id="22cf9-126">Имя поставщика программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="22cf9-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="22cf9-127">string</span><span class="sxs-lookup"><span data-stu-id="22cf9-127">string</span></span> | <span data-ttu-id="22cf9-128">Название программного продукта</span><span class="sxs-lookup"><span data-stu-id="22cf9-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="22cf9-129">string</span><span class="sxs-lookup"><span data-stu-id="22cf9-129">string</span></span> | <span data-ttu-id="22cf9-130">Номер версии программного продукта</span><span class="sxs-lookup"><span data-stu-id="22cf9-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="22cf9-131">string</span><span class="sxs-lookup"><span data-stu-id="22cf9-131">string</span></span> | <span data-ttu-id="22cf9-132">Уникальный идентификатор, назначенный уязвимости в системе общеизвестных уязвимостей и рисков (CVE)</span><span class="sxs-lookup"><span data-stu-id="22cf9-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="22cf9-133">string</span><span class="sxs-lookup"><span data-stu-id="22cf9-133">string</span></span> | <span data-ttu-id="22cf9-134">Уровень серьезности, назначенный уязвимости безопасности на основе оценки CVSS и динамических коэффициентов, на которые влияет обстановка с угрозами</span><span class="sxs-lookup"><span data-stu-id="22cf9-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="22cf9-135">См. также</span><span class="sxs-lookup"><span data-stu-id="22cf9-135">Related topics</span></span>

- [<span data-ttu-id="22cf9-136">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="22cf9-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="22cf9-137">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="22cf9-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="22cf9-138">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="22cf9-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="22cf9-139">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="22cf9-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="22cf9-140">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="22cf9-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="22cf9-141">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="22cf9-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="22cf9-142">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="22cf9-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
