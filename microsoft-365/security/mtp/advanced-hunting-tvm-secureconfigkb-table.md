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
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 2bcf3ab438dc8894c186ac7ee477af1821e783cc
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210184"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="01a6d-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="01a6d-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="01a6d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="01a6d-105">**Applies to:**</span></span>
- <span data-ttu-id="01a6d-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="01a6d-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="01a6d-107">В таблице `DeviceTvmSecureConfigurationAssessmentKB` в схеме расширенного поиска содержатся сведения о различных настройках безопасности,— в том числе сведения о том, включено ли на устройстве автоматическое обновление, — которые проверяются с помощью [Контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="01a6d-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="01a6d-108">Кроме того, в ней также содержатся сведения о рисках, связанных отраслевых контрольных показателях, а также о применимых приемах и тактиках MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="01a6d-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="01a6d-109">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="01a6d-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="01a6d-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="01a6d-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="01a6d-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="01a6d-111">Column name</span></span> | <span data-ttu-id="01a6d-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="01a6d-112">Data type</span></span> | <span data-ttu-id="01a6d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="01a6d-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="01a6d-114">string</span><span class="sxs-lookup"><span data-stu-id="01a6d-114">string</span></span> | <span data-ttu-id="01a6d-115">Уникальный идентификатор определенной настройки</span><span class="sxs-lookup"><span data-stu-id="01a6d-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="01a6d-116">string</span><span class="sxs-lookup"><span data-stu-id="01a6d-116">string</span></span> | <span data-ttu-id="01a6d-117">Оценка влияния настройки на общую оценку конфигурации (1–10)</span><span class="sxs-lookup"><span data-stu-id="01a6d-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="01a6d-118">string</span><span class="sxs-lookup"><span data-stu-id="01a6d-118">string</span></span> | <span data-ttu-id="01a6d-119">Отображение названия настройки</span><span class="sxs-lookup"><span data-stu-id="01a6d-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="01a6d-120">string</span><span class="sxs-lookup"><span data-stu-id="01a6d-120">string</span></span> | <span data-ttu-id="01a6d-121">Описание ошибки настройки</span><span class="sxs-lookup"><span data-stu-id="01a6d-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="01a6d-122">string</span><span class="sxs-lookup"><span data-stu-id="01a6d-122">string</span></span> | <span data-ttu-id="01a6d-123">Описание связанного риска</span><span class="sxs-lookup"><span data-stu-id="01a6d-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="01a6d-124">string</span><span class="sxs-lookup"><span data-stu-id="01a6d-124">string</span></span> | <span data-ttu-id="01a6d-125">Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности</span><span class="sxs-lookup"><span data-stu-id="01a6d-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="01a6d-126">string</span><span class="sxs-lookup"><span data-stu-id="01a6d-126">string</span></span> |<span data-ttu-id="01a6d-127">Подкатегория или подгруппа, к которой относится настройка.</span><span class="sxs-lookup"><span data-stu-id="01a6d-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="01a6d-128">Во многих случаях здесь описываются конкретные возможности или функции.</span><span class="sxs-lookup"><span data-stu-id="01a6d-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="01a6d-129">string</span><span class="sxs-lookup"><span data-stu-id="01a6d-129">string</span></span> | <span data-ttu-id="01a6d-130">Список отраслевых контрольных показателей с рекомендациями по аналогичной или схожей настройке</span><span class="sxs-lookup"><span data-stu-id="01a6d-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="01a6d-131">string</span><span class="sxs-lookup"><span data-stu-id="01a6d-131">string</span></span> | <span data-ttu-id="01a6d-132">Список приемов платформы Mitre ATT&CK, относящихся к настройке</span><span class="sxs-lookup"><span data-stu-id="01a6d-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="01a6d-133">string</span><span class="sxs-lookup"><span data-stu-id="01a6d-133">string</span></span> | <span data-ttu-id="01a6d-134">Список тактик платформы Mitre ATT&CK, относящихся к настройке</span><span class="sxs-lookup"><span data-stu-id="01a6d-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="01a6d-135">См. также</span><span class="sxs-lookup"><span data-stu-id="01a6d-135">Related topics</span></span>

- [<span data-ttu-id="01a6d-136">Профилактический поиск угроз</span><span class="sxs-lookup"><span data-stu-id="01a6d-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="01a6d-137">Сведения о языке запросов</span><span class="sxs-lookup"><span data-stu-id="01a6d-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="01a6d-138">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="01a6d-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="01a6d-139">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="01a6d-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="01a6d-140">Общие сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="01a6d-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="01a6d-141">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="01a6d-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="01a6d-142">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="01a6d-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
