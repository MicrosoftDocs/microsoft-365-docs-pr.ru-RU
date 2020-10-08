---
title: Таблица DeviceTvmSecureConfigurationAssessmentKB в схеме расширенного поиска угроз
description: Узнайте о различных настройках безопасности, оцененных в Контроле угроз и уязвимостей, в таблице DeviceTvmSecureConfigurationAssessmentKB схемы расширенного поиска угроз.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справочник по схемам, Кусто, таблица, столбец, тип данных, описание, угроза & уязвимости, ТВМ, Управление устройствами, Настройка безопасности, МИТРЕ ATT&а Framework, база знаний, KB, Девицетвмсекуреконфигуратионассессменткб
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
ms.openlocfilehash: 3960d877ed1807d2e8ac13512f9bdbb1625fc371
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198125"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="c02a8-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="c02a8-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c02a8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c02a8-105">**Applies to:**</span></span>
- <span data-ttu-id="c02a8-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c02a8-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="c02a8-107">В таблице `DeviceTvmSecureConfigurationAssessmentKB` в схеме расширенного поиска содержатся сведения о различных настройках безопасности,— в том числе сведения о том, включено ли на устройстве автоматическое обновление, — которые проверяются с помощью [Контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="c02a8-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="c02a8-108">Кроме того, в ней также содержатся сведения о рисках, связанных отраслевых контрольных показателях, а также о применимых приемах и тактиках MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="c02a8-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="c02a8-109">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="c02a8-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="c02a8-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c02a8-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c02a8-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="c02a8-111">Column name</span></span> | <span data-ttu-id="c02a8-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c02a8-112">Data type</span></span> | <span data-ttu-id="c02a8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c02a8-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="c02a8-114">string</span><span class="sxs-lookup"><span data-stu-id="c02a8-114">string</span></span> | <span data-ttu-id="c02a8-115">Уникальный идентификатор определенной настройки</span><span class="sxs-lookup"><span data-stu-id="c02a8-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="c02a8-116">string</span><span class="sxs-lookup"><span data-stu-id="c02a8-116">string</span></span> | <span data-ttu-id="c02a8-117">Оценка влияния настройки на общую оценку конфигурации (1–10)</span><span class="sxs-lookup"><span data-stu-id="c02a8-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="c02a8-118">string</span><span class="sxs-lookup"><span data-stu-id="c02a8-118">string</span></span> | <span data-ttu-id="c02a8-119">Отображение названия настройки</span><span class="sxs-lookup"><span data-stu-id="c02a8-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="c02a8-120">string</span><span class="sxs-lookup"><span data-stu-id="c02a8-120">string</span></span> | <span data-ttu-id="c02a8-121">Описание ошибки настройки</span><span class="sxs-lookup"><span data-stu-id="c02a8-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="c02a8-122">string</span><span class="sxs-lookup"><span data-stu-id="c02a8-122">string</span></span> | <span data-ttu-id="c02a8-123">Описание связанного риска</span><span class="sxs-lookup"><span data-stu-id="c02a8-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="c02a8-124">string</span><span class="sxs-lookup"><span data-stu-id="c02a8-124">string</span></span> | <span data-ttu-id="c02a8-125">Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности</span><span class="sxs-lookup"><span data-stu-id="c02a8-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="c02a8-126">string</span><span class="sxs-lookup"><span data-stu-id="c02a8-126">string</span></span> |<span data-ttu-id="c02a8-127">Подкатегория или подгруппа, к которой относится настройка.</span><span class="sxs-lookup"><span data-stu-id="c02a8-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="c02a8-128">Во многих случаях здесь описываются конкретные возможности или функции.</span><span class="sxs-lookup"><span data-stu-id="c02a8-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="c02a8-129">string</span><span class="sxs-lookup"><span data-stu-id="c02a8-129">string</span></span> | <span data-ttu-id="c02a8-130">Список отраслевых контрольных показателей с рекомендациями по аналогичной или схожей настройке</span><span class="sxs-lookup"><span data-stu-id="c02a8-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="c02a8-131">string</span><span class="sxs-lookup"><span data-stu-id="c02a8-131">string</span></span> | <span data-ttu-id="c02a8-132">Список приемов платформы Mitre ATT&CK, относящихся к настройке</span><span class="sxs-lookup"><span data-stu-id="c02a8-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="c02a8-133">string</span><span class="sxs-lookup"><span data-stu-id="c02a8-133">string</span></span> | <span data-ttu-id="c02a8-134">Список тактик платформы Mitre ATT&CK, относящихся к настройке</span><span class="sxs-lookup"><span data-stu-id="c02a8-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c02a8-135">См. также</span><span class="sxs-lookup"><span data-stu-id="c02a8-135">Related topics</span></span>

- [<span data-ttu-id="c02a8-136">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="c02a8-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c02a8-137">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="c02a8-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c02a8-138">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="c02a8-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c02a8-139">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="c02a8-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c02a8-140">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="c02a8-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c02a8-141">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="c02a8-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c02a8-142">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="c02a8-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
