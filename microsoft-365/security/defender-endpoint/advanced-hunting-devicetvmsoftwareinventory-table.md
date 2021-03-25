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
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075542"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="00a02-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="00a02-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="00a02-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="00a02-105">**Applies to:**</span></span>
- [<span data-ttu-id="00a02-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="00a02-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="00a02-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="00a02-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="00a02-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="00a02-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="00a02-109">Таблица в продвинутой схеме охоты содержит инвентаризацию программного обеспечения управления & уязвимостей, установленного в настоящее время на устройствах в вашей сети, включая конечные сведения `DeviceTvmSoftwareInventory` о поддержке. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="00a02-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="00a02-110">Например, можно искать события, связанные с устройствами, установленными с уязвимой в настоящее время версией программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="00a02-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="00a02-111">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="00a02-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="00a02-112">Таблицы `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` и таблицы заменили `DeviceTvmSoftwareInventoryVulnerabilities` таблицу.</span><span class="sxs-lookup"><span data-stu-id="00a02-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="00a02-113">В первых двух таблицах содержится больше столбцов, которые можно использовать для информирования о действиях по управлению уязвимостями.</span><span class="sxs-lookup"><span data-stu-id="00a02-113">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="00a02-114">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="00a02-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="00a02-115">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="00a02-115">Column name</span></span> | <span data-ttu-id="00a02-116">Тип данных</span><span class="sxs-lookup"><span data-stu-id="00a02-116">Data type</span></span> | <span data-ttu-id="00a02-117">Описание</span><span class="sxs-lookup"><span data-stu-id="00a02-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="00a02-118">string</span><span class="sxs-lookup"><span data-stu-id="00a02-118">string</span></span> | <span data-ttu-id="00a02-119">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="00a02-119">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="00a02-120">строка</span><span class="sxs-lookup"><span data-stu-id="00a02-120">string</span></span> | <span data-ttu-id="00a02-121">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="00a02-121">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="00a02-122">строка</span><span class="sxs-lookup"><span data-stu-id="00a02-122">string</span></span> | <span data-ttu-id="00a02-123">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="00a02-123">Platform of the operating system running on the device.</span></span> <span data-ttu-id="00a02-124">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="00a02-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="00a02-125">string</span><span class="sxs-lookup"><span data-stu-id="00a02-125">string</span></span> | <span data-ttu-id="00a02-126">Версия операционной системы, запущенной на устройстве</span><span class="sxs-lookup"><span data-stu-id="00a02-126">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="00a02-127">строка</span><span class="sxs-lookup"><span data-stu-id="00a02-127">string</span></span> | <span data-ttu-id="00a02-128">Архитектура операционной системы, запущенной на устройстве</span><span class="sxs-lookup"><span data-stu-id="00a02-128">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="00a02-129">строка</span><span class="sxs-lookup"><span data-stu-id="00a02-129">string</span></span> | <span data-ttu-id="00a02-130">Имя поставщика программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="00a02-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="00a02-131">string</span><span class="sxs-lookup"><span data-stu-id="00a02-131">string</span></span> | <span data-ttu-id="00a02-132">Название программного продукта</span><span class="sxs-lookup"><span data-stu-id="00a02-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="00a02-133">string</span><span class="sxs-lookup"><span data-stu-id="00a02-133">string</span></span> | <span data-ttu-id="00a02-134">Номер версии программного продукта</span><span class="sxs-lookup"><span data-stu-id="00a02-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="00a02-135">string</span><span class="sxs-lookup"><span data-stu-id="00a02-135">string</span></span> | <span data-ttu-id="00a02-136">Указывает этап жизненного цикла программного продукта относительно указанной даты окончания поддержки (EOS) или даты окончания срока службы (EOL).</span><span class="sxs-lookup"><span data-stu-id="00a02-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="00a02-137">строка</span><span class="sxs-lookup"><span data-stu-id="00a02-137">string</span></span> | <span data-ttu-id="00a02-138">Дата окончания службы поддержки (EOS) или даты окончания срока службы программного продукта</span><span class="sxs-lookup"><span data-stu-id="00a02-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="00a02-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="00a02-139">Related topics</span></span>

- [<span data-ttu-id="00a02-140">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="00a02-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="00a02-141">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="00a02-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="00a02-142">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="00a02-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="00a02-143">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="00a02-143">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)

