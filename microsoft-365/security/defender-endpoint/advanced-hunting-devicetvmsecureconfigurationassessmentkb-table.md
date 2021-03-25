---
title: Таблица DeviceTvmSecureConfigurationAssessmentKB в схеме расширенного поиска угроз
description: Узнайте о различных безопасных конфигурациях, оцениваемой управлением & уязвимостей, в таблице DeviceTvmSecureConfigurationAssessmentKB схемы advanced hunting.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, MITRE ATT&CK framework, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 3ba0d90fae872eff209b41b7ba62baeccfe62808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075045"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="61fb5-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="61fb5-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="61fb5-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="61fb5-105">**Applies to:**</span></span>
- [<span data-ttu-id="61fb5-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="61fb5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="61fb5-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="61fb5-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="61fb5-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="61fb5-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="61fb5-109">В таблице `DeviceTvmSecureConfigurationAssessmentKB` в схеме расширенного поиска содержатся сведения о различных настройках безопасности,— в том числе сведения о том, включено ли на устройстве автоматическое обновление, — которые проверяются с помощью [Контроля угроз и уязвимостей](next-gen-threat-and-vuln-mgt.md).</span><span class="sxs-lookup"><span data-stu-id="61fb5-109">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="61fb5-110">Кроме того, в ней также содержатся сведения о рисках, связанных отраслевых контрольных показателях, а также о применимых приемах и тактиках MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="61fb5-110">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="61fb5-111">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="61fb5-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="61fb5-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="61fb5-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="61fb5-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="61fb5-113">Column name</span></span> | <span data-ttu-id="61fb5-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="61fb5-114">Data type</span></span> | <span data-ttu-id="61fb5-115">Описание</span><span class="sxs-lookup"><span data-stu-id="61fb5-115">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="61fb5-116">string</span><span class="sxs-lookup"><span data-stu-id="61fb5-116">string</span></span> | <span data-ttu-id="61fb5-117">Уникальный идентификатор определенной настройки</span><span class="sxs-lookup"><span data-stu-id="61fb5-117">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="61fb5-118">string</span><span class="sxs-lookup"><span data-stu-id="61fb5-118">string</span></span> | <span data-ttu-id="61fb5-119">Оценка влияния настройки на общую оценку конфигурации (1–10)</span><span class="sxs-lookup"><span data-stu-id="61fb5-119">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="61fb5-120">string</span><span class="sxs-lookup"><span data-stu-id="61fb5-120">string</span></span> | <span data-ttu-id="61fb5-121">Отображение названия настройки</span><span class="sxs-lookup"><span data-stu-id="61fb5-121">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="61fb5-122">string</span><span class="sxs-lookup"><span data-stu-id="61fb5-122">string</span></span> | <span data-ttu-id="61fb5-123">Описание ошибки настройки</span><span class="sxs-lookup"><span data-stu-id="61fb5-123">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="61fb5-124">string</span><span class="sxs-lookup"><span data-stu-id="61fb5-124">string</span></span> | <span data-ttu-id="61fb5-125">Описание связанного риска</span><span class="sxs-lookup"><span data-stu-id="61fb5-125">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="61fb5-126">string</span><span class="sxs-lookup"><span data-stu-id="61fb5-126">string</span></span> | <span data-ttu-id="61fb5-127">Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности</span><span class="sxs-lookup"><span data-stu-id="61fb5-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="61fb5-128">string</span><span class="sxs-lookup"><span data-stu-id="61fb5-128">string</span></span> |<span data-ttu-id="61fb5-129">Подкатегория или подгруппа, к которой относится настройка.</span><span class="sxs-lookup"><span data-stu-id="61fb5-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="61fb5-130">Во многих случаях здесь описываются конкретные возможности или функции.</span><span class="sxs-lookup"><span data-stu-id="61fb5-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="61fb5-131">string</span><span class="sxs-lookup"><span data-stu-id="61fb5-131">string</span></span> | <span data-ttu-id="61fb5-132">Список отраслевых контрольных показателей с рекомендациями по аналогичной или схожей настройке</span><span class="sxs-lookup"><span data-stu-id="61fb5-132">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="61fb5-133">string</span><span class="sxs-lookup"><span data-stu-id="61fb5-133">string</span></span> | <span data-ttu-id="61fb5-134">Список приемов платформы Mitre ATT&CK, относящихся к настройке</span><span class="sxs-lookup"><span data-stu-id="61fb5-134">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="61fb5-135">string</span><span class="sxs-lookup"><span data-stu-id="61fb5-135">string</span></span> | <span data-ttu-id="61fb5-136">Список тактик платформы Mitre ATT&CK, относящихся к настройке</span><span class="sxs-lookup"><span data-stu-id="61fb5-136">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="61fb5-137">См. также</span><span class="sxs-lookup"><span data-stu-id="61fb5-137">Related topics</span></span>

- [<span data-ttu-id="61fb5-138">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="61fb5-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="61fb5-139">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="61fb5-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="61fb5-140">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="61fb5-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="61fb5-141">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="61fb5-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
