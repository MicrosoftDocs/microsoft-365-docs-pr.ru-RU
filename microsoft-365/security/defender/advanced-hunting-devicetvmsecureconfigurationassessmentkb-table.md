---
title: Таблица DeviceTvmSecureConfigurationAssessmentKB в схеме расширенного поиска угроз
description: Узнайте о различных настройках безопасности, оцененных в Контроле угроз и уязвимостей, в таблице DeviceTvmSecureConfigurationAssessmentKB схемы расширенного поиска угроз.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, MITRE ATT&CK framework, knowledge base, KB, DeviceTvSecureConfigurationAssessment
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e664f0da29e0403b415792c839fd740006791cf0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071494"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="9e4ab-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="9e4ab-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9e4ab-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9e4ab-105">**Applies to:**</span></span>
- <span data-ttu-id="9e4ab-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e4ab-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="9e4ab-107">В таблице `DeviceTvmSecureConfigurationAssessmentKB` в схеме расширенного поиска содержатся сведения о различных настройках безопасности,— в том числе сведения о том, включено ли на устройстве автоматическое обновление, — которые проверяются с помощью [Контроля угроз и уязвимостей](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="9e4ab-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="9e4ab-108">Кроме того, в ней также содержатся сведения о рисках, связанных отраслевых контрольных показателях, а также о применимых приемах и тактиках MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="9e4ab-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="9e4ab-109">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="9e4ab-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="9e4ab-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9e4ab-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9e4ab-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="9e4ab-111">Column name</span></span> | <span data-ttu-id="9e4ab-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="9e4ab-112">Data type</span></span> | <span data-ttu-id="9e4ab-113">Описание</span><span class="sxs-lookup"><span data-stu-id="9e4ab-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="9e4ab-114">string</span><span class="sxs-lookup"><span data-stu-id="9e4ab-114">string</span></span> | <span data-ttu-id="9e4ab-115">Уникальный идентификатор определенной настройки</span><span class="sxs-lookup"><span data-stu-id="9e4ab-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="9e4ab-116">string</span><span class="sxs-lookup"><span data-stu-id="9e4ab-116">string</span></span> | <span data-ttu-id="9e4ab-117">Оценка влияния настройки на общую оценку конфигурации (1–10)</span><span class="sxs-lookup"><span data-stu-id="9e4ab-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="9e4ab-118">string</span><span class="sxs-lookup"><span data-stu-id="9e4ab-118">string</span></span> | <span data-ttu-id="9e4ab-119">Отображение названия настройки</span><span class="sxs-lookup"><span data-stu-id="9e4ab-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="9e4ab-120">string</span><span class="sxs-lookup"><span data-stu-id="9e4ab-120">string</span></span> | <span data-ttu-id="9e4ab-121">Описание ошибки настройки</span><span class="sxs-lookup"><span data-stu-id="9e4ab-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="9e4ab-122">string</span><span class="sxs-lookup"><span data-stu-id="9e4ab-122">string</span></span> | <span data-ttu-id="9e4ab-123">Описание связанного риска</span><span class="sxs-lookup"><span data-stu-id="9e4ab-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="9e4ab-124">string</span><span class="sxs-lookup"><span data-stu-id="9e4ab-124">string</span></span> | <span data-ttu-id="9e4ab-125">Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности</span><span class="sxs-lookup"><span data-stu-id="9e4ab-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="9e4ab-126">string</span><span class="sxs-lookup"><span data-stu-id="9e4ab-126">string</span></span> |<span data-ttu-id="9e4ab-127">Подкатегория или подгруппа, к которой относится настройка.</span><span class="sxs-lookup"><span data-stu-id="9e4ab-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="9e4ab-128">Во многих случаях здесь описываются конкретные возможности или функции.</span><span class="sxs-lookup"><span data-stu-id="9e4ab-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="9e4ab-129">string</span><span class="sxs-lookup"><span data-stu-id="9e4ab-129">string</span></span> | <span data-ttu-id="9e4ab-130">Список отраслевых контрольных показателей с рекомендациями по аналогичной или схожей настройке</span><span class="sxs-lookup"><span data-stu-id="9e4ab-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="9e4ab-131">string</span><span class="sxs-lookup"><span data-stu-id="9e4ab-131">string</span></span> | <span data-ttu-id="9e4ab-132">Метки, представляющие различные атрибуты, используемые для определения или классификации конфигурации безопасности</span><span class="sxs-lookup"><span data-stu-id="9e4ab-132">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="9e4ab-133">строка</span><span class="sxs-lookup"><span data-stu-id="9e4ab-133">string</span></span> | <span data-ttu-id="9e4ab-134">Рекомендуемые действия по снижению или устранению связанных рисков</span><span class="sxs-lookup"><span data-stu-id="9e4ab-134">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9e4ab-135">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9e4ab-135">Related topics</span></span>

- [<span data-ttu-id="9e4ab-136">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="9e4ab-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9e4ab-137">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="9e4ab-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9e4ab-138">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="9e4ab-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9e4ab-139">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="9e4ab-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9e4ab-140">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="9e4ab-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9e4ab-141">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="9e4ab-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="9e4ab-142">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="9e4ab-142">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)