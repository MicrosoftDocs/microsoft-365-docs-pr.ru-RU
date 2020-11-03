---
title: Таблица DeviceTvmSecureConfigurationAssessment в схеме расширенной охоты
description: Сведения о событиях оценки безопасности в таблице Девицетвмсекуреконфигуратионассессмент расширенной схемы подсистемы поискового подсистемы. Эти & угрозами события управления уязвимостью предоставляют сведения об устройствах, а также сведения о конфигурации безопасности, влияние и соответствие требованиям.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, угроза & уязвимости, ТВМ, Управление устройствами, Настройка безопасности, Девицетвмсекуреконфигуратионассессмент
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: bfe63397d194567a7d71de703363083d2fd4fe75
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847612"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="582e4-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="582e4-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="582e4-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="582e4-106">**Applies to:**</span></span>
- <span data-ttu-id="582e4-107">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="582e4-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="582e4-108">Каждая строка в таблице `DeviceTvmSecureConfigurationAssessment` содержит событие оценки для определенной настройки безопасности от функции [контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="582e4-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="582e4-109">Используйте этот справочник для проверки последних результатов оценки и определения соответствия устройства требованиям.</span><span class="sxs-lookup"><span data-stu-id="582e4-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="582e4-110">Сведения о других таблицах в схеме расширенной охоты см. в [справочнике по расширенной охоте](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="582e4-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="582e4-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="582e4-111">Column name</span></span> | <span data-ttu-id="582e4-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="582e4-112">Data type</span></span> | <span data-ttu-id="582e4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="582e4-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="582e4-114">string</span><span class="sxs-lookup"><span data-stu-id="582e4-114">string</span></span> | <span data-ttu-id="582e4-115">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="582e4-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="582e4-116">string</span><span class="sxs-lookup"><span data-stu-id="582e4-116">string</span></span> | <span data-ttu-id="582e4-117">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="582e4-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="582e4-118">string</span><span class="sxs-lookup"><span data-stu-id="582e4-118">string</span></span> | <span data-ttu-id="582e4-119">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="582e4-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="582e4-120">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="582e4-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="582e4-121">datetime</span><span class="sxs-lookup"><span data-stu-id="582e4-121">datetime</span></span> | <span data-ttu-id="582e4-122">Дата и время создания записи</span><span class="sxs-lookup"><span data-stu-id="582e4-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="582e4-123">string</span><span class="sxs-lookup"><span data-stu-id="582e4-123">string</span></span> | <span data-ttu-id="582e4-124">Уникальный идентификатор определенной настройки</span><span class="sxs-lookup"><span data-stu-id="582e4-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="582e4-125">string</span><span class="sxs-lookup"><span data-stu-id="582e4-125">string</span></span> | <span data-ttu-id="582e4-126">Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности</span><span class="sxs-lookup"><span data-stu-id="582e4-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="582e4-127">string</span><span class="sxs-lookup"><span data-stu-id="582e4-127">string</span></span> | <span data-ttu-id="582e4-128">Подкатегория или подгруппа, к которой относится настройка.</span><span class="sxs-lookup"><span data-stu-id="582e4-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="582e4-129">Во многих случаях здесь описываются конкретные возможности или функции.</span><span class="sxs-lookup"><span data-stu-id="582e4-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="582e4-130">string</span><span class="sxs-lookup"><span data-stu-id="582e4-130">string</span></span> | <span data-ttu-id="582e4-131">Оценка влияния настройки на общую оценку конфигурации (1–10)</span><span class="sxs-lookup"><span data-stu-id="582e4-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="582e4-132">boolean</span><span class="sxs-lookup"><span data-stu-id="582e4-132">boolean</span></span> | <span data-ttu-id="582e4-133">Указывает, правильно ли настроена конфигурация или политика</span><span class="sxs-lookup"><span data-stu-id="582e4-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="582e4-134">boolean</span><span class="sxs-lookup"><span data-stu-id="582e4-134">boolean</span></span> | <span data-ttu-id="582e4-135">Указывает, применяется ли конфигурация или политика к устройству.</span><span class="sxs-lookup"><span data-stu-id="582e4-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="582e4-136">string</span><span class="sxs-lookup"><span data-stu-id="582e4-136">string</span></span> | <span data-ttu-id="582e4-137">Дополнительные контекстные сведения о конфигурации или политике</span><span class="sxs-lookup"><span data-stu-id="582e4-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="582e4-138">boolean</span><span class="sxs-lookup"><span data-stu-id="582e4-138">boolean</span></span> | <span data-ttu-id="582e4-139">Указывает, будет ли оказывать влияние пользователь при применении конфигурации или политики</span><span class="sxs-lookup"><span data-stu-id="582e4-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="582e4-140">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="582e4-140">Related topics</span></span>

- [<span data-ttu-id="582e4-141">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="582e4-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="582e4-142">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="582e4-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="582e4-143">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="582e4-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="582e4-144">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="582e4-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="582e4-145">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="582e4-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="582e4-146">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="582e4-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="582e4-147">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="582e4-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
