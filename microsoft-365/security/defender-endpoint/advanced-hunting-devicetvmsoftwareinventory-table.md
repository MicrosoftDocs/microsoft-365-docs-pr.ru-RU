---
title: DeviceTvmSoftwareInventory table in the advanced hunting schema
description: Узнайте о инвентаризации программного обеспечения на устройствах в таблице DeviceTvmSoftwareInventory продвинутой схемы охоты.
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
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408627"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="0822d-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="0822d-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0822d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0822d-105">**Applies to:**</span></span>
- [<span data-ttu-id="0822d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0822d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="0822d-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="0822d-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0822d-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="0822d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="0822d-109">Таблица в продвинутой схеме охоты содержит инвентаризацию программного обеспечения для управления угрозами и уязвимостями, установленного в настоящее время на устройствах в сети, включая конец сведений `DeviceTvmSoftwareInventory` о поддержке. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="0822d-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="0822d-110">Например, можно искать события, связанные с устройствами, установленными с уязвимой в настоящее время версией программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="0822d-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="0822d-111">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="0822d-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="0822d-112">DeviceTVMSoftwareInventory содержит все программное обеспечение, которое управление угрозами и уязвимостью было в состоянии соответствовать общему переумывке платформы (CPE) — является ли оно уязвимым или нет.</span><span class="sxs-lookup"><span data-stu-id="0822d-112">DeviceTVMSoftwareInventory contains all the software which threat and vulnerability management was able to match to a Common Platform Enumeration (CPE) – whether it is vulnerable or not.</span></span>

>[!NOTE]
><span data-ttu-id="0822d-113">Таблицы `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` и таблицы заменили `DeviceTvmSoftwareInventoryVulnerabilities` таблицу.</span><span class="sxs-lookup"><span data-stu-id="0822d-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="0822d-114">В первых двух таблицах содержится больше столбцов, которые можно использовать для информирования о действиях по управлению уязвимостями.</span><span class="sxs-lookup"><span data-stu-id="0822d-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="0822d-115">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="0822d-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="0822d-116">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="0822d-116">Column name</span></span> | <span data-ttu-id="0822d-117">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0822d-117">Data type</span></span> | <span data-ttu-id="0822d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="0822d-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="0822d-119">string</span><span class="sxs-lookup"><span data-stu-id="0822d-119">string</span></span> | <span data-ttu-id="0822d-120">Уникальный идентификатор устройства в службе.</span><span class="sxs-lookup"><span data-stu-id="0822d-120">Unique identifier for the device in the service.</span></span> |
| `DeviceName` | <span data-ttu-id="0822d-121">Строка</span><span class="sxs-lookup"><span data-stu-id="0822d-121">string</span></span> | <span data-ttu-id="0822d-122">Полное доменное имя (FQDN) устройства.</span><span class="sxs-lookup"><span data-stu-id="0822d-122">Fully qualified domain name (FQDN) of the device.</span></span> |
| `OSPlatform` | <span data-ttu-id="0822d-123">Строка</span><span class="sxs-lookup"><span data-stu-id="0822d-123">string</span></span> | <span data-ttu-id="0822d-124">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="0822d-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="0822d-125">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="0822d-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="0822d-126">string</span><span class="sxs-lookup"><span data-stu-id="0822d-126">string</span></span> | <span data-ttu-id="0822d-127">Версия операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="0822d-127">Version of the operating system running on the device.</span></span> |
| `OSArchitecture` | <span data-ttu-id="0822d-128">Строка</span><span class="sxs-lookup"><span data-stu-id="0822d-128">string</span></span> | <span data-ttu-id="0822d-129">Архитектура операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="0822d-129">Architecture of the operating system running on the device.</span></span> |
| `SoftwareVendor` | <span data-ttu-id="0822d-130">Строка</span><span class="sxs-lookup"><span data-stu-id="0822d-130">string</span></span> | <span data-ttu-id="0822d-131">Имя поставщика программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="0822d-131">Name of the software vendor.</span></span> |
| `SoftwareName` | <span data-ttu-id="0822d-132">Строка</span><span class="sxs-lookup"><span data-stu-id="0822d-132">string</span></span> | <span data-ttu-id="0822d-133">Имя программного продукта.</span><span class="sxs-lookup"><span data-stu-id="0822d-133">Name of the software product.</span></span> |
| `SoftwareVersion` | <span data-ttu-id="0822d-134">Строка</span><span class="sxs-lookup"><span data-stu-id="0822d-134">string</span></span> | <span data-ttu-id="0822d-135">Номер версии программного продукта.</span><span class="sxs-lookup"><span data-stu-id="0822d-135">Version number of the software product.</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="0822d-136">Строка</span><span class="sxs-lookup"><span data-stu-id="0822d-136">string</span></span> | <span data-ttu-id="0822d-137">Указывает этап жизненного цикла программного продукта относительно указанной даты окончания службы поддержки (EOS) или даты окончания срока службы (EOL).</span><span class="sxs-lookup"><span data-stu-id="0822d-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date.</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="0822d-138">Строка</span><span class="sxs-lookup"><span data-stu-id="0822d-138">string</span></span> | <span data-ttu-id="0822d-139">Дата окончания службы поддержки (EOS) или дата окончания срока службы программного продукта.</span><span class="sxs-lookup"><span data-stu-id="0822d-139">End-of-support (EOS) or end-of-life (EOL) date of the software product.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0822d-140">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0822d-140">Related topics</span></span>

- [<span data-ttu-id="0822d-141">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="0822d-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0822d-142">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="0822d-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0822d-143">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="0822d-143">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="0822d-144">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="0822d-144">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
