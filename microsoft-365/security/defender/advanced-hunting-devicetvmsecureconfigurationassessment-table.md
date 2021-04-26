---
title: Таблица DeviceTvmSecureConfigurationAssessment в схеме расширенной охоты
description: Узнайте о событиях оценки безопасности в таблице DeviceTvmSecureConfigurationAssessment продвинутой схемы охоты. Эти события & управления уязвимостями предоставляют сведения об устройстве, а также сведения о конфигурации безопасности, последствиях и соответствия требованиям.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 2e3e649911cb2ce63c2a49be0ebc93e35e8055d6
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024221"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="18bc6-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="18bc6-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="18bc6-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="18bc6-106">**Applies to:**</span></span>
- <span data-ttu-id="18bc6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18bc6-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="18bc6-108">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="18bc6-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="18bc6-109">Каждая строка в таблице `DeviceTvmSecureConfigurationAssessment` содержит событие оценки для определенной настройки безопасности от функции [контроля угроз и уязвимостей](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="18bc6-109">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="18bc6-110">Используйте этот справочник для проверки последних результатов оценки и определения соответствия устройства требованиям.</span><span class="sxs-lookup"><span data-stu-id="18bc6-110">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="18bc6-111">Сведения о других таблицах в схеме расширенной охоты см. в [справочнике по расширенной охоте](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="18bc6-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="18bc6-112">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="18bc6-112">Column name</span></span> | <span data-ttu-id="18bc6-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="18bc6-113">Data type</span></span> | <span data-ttu-id="18bc6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="18bc6-114">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="18bc6-115">string</span><span class="sxs-lookup"><span data-stu-id="18bc6-115">string</span></span> | <span data-ttu-id="18bc6-116">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="18bc6-116">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="18bc6-117">String</span><span class="sxs-lookup"><span data-stu-id="18bc6-117">string</span></span> | <span data-ttu-id="18bc6-118">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="18bc6-118">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="18bc6-119">String</span><span class="sxs-lookup"><span data-stu-id="18bc6-119">string</span></span> | <span data-ttu-id="18bc6-120">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="18bc6-120">Platform of the operating system running on the device.</span></span> <span data-ttu-id="18bc6-121">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="18bc6-121">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="18bc6-122">datetime</span><span class="sxs-lookup"><span data-stu-id="18bc6-122">datetime</span></span> | <span data-ttu-id="18bc6-123">Дата и время создания записи</span><span class="sxs-lookup"><span data-stu-id="18bc6-123">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="18bc6-124">string</span><span class="sxs-lookup"><span data-stu-id="18bc6-124">string</span></span> | <span data-ttu-id="18bc6-125">Уникальный идентификатор определенной настройки</span><span class="sxs-lookup"><span data-stu-id="18bc6-125">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="18bc6-126">string</span><span class="sxs-lookup"><span data-stu-id="18bc6-126">string</span></span> | <span data-ttu-id="18bc6-127">Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности</span><span class="sxs-lookup"><span data-stu-id="18bc6-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="18bc6-128">string</span><span class="sxs-lookup"><span data-stu-id="18bc6-128">string</span></span> | <span data-ttu-id="18bc6-129">Подкатегория или подгруппа, к которой относится настройка.</span><span class="sxs-lookup"><span data-stu-id="18bc6-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="18bc6-130">Во многих случаях здесь описываются конкретные возможности или функции.</span><span class="sxs-lookup"><span data-stu-id="18bc6-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="18bc6-131">string</span><span class="sxs-lookup"><span data-stu-id="18bc6-131">string</span></span> | <span data-ttu-id="18bc6-132">Оценка влияния настройки на общую оценку конфигурации (1–10)</span><span class="sxs-lookup"><span data-stu-id="18bc6-132">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="18bc6-133">boolean</span><span class="sxs-lookup"><span data-stu-id="18bc6-133">boolean</span></span> | <span data-ttu-id="18bc6-134">Указывает, правильно ли настроена конфигурация или политика</span><span class="sxs-lookup"><span data-stu-id="18bc6-134">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="18bc6-135">boolean</span><span class="sxs-lookup"><span data-stu-id="18bc6-135">boolean</span></span> | <span data-ttu-id="18bc6-136">Указывает, применима ли конфигурация или политика к устройству</span><span class="sxs-lookup"><span data-stu-id="18bc6-136">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="18bc6-137">String</span><span class="sxs-lookup"><span data-stu-id="18bc6-137">string</span></span> | <span data-ttu-id="18bc6-138">Дополнительные контекстные сведения о конфигурации или политике</span><span class="sxs-lookup"><span data-stu-id="18bc6-138">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpact` | <span data-ttu-id="18bc6-139">boolean</span><span class="sxs-lookup"><span data-stu-id="18bc6-139">boolean</span></span> | <span data-ttu-id="18bc6-140">Указывает, будет ли влияние пользователя, если применяется конфигурация или политика</span><span class="sxs-lookup"><span data-stu-id="18bc6-140">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="18bc6-141">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="18bc6-141">Related topics</span></span>

- [<span data-ttu-id="18bc6-142">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="18bc6-142">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="18bc6-143">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="18bc6-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="18bc6-144">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="18bc6-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="18bc6-145">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="18bc6-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="18bc6-146">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="18bc6-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="18bc6-147">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="18bc6-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="18bc6-148">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="18bc6-148">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)