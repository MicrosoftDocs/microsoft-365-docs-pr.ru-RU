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
ms.openlocfilehash: 356548c3115aacce8c76d7fbc552811c168750ed
ms.sourcegitcommit: e8b3855302fc34d09b6df6c737033a2f326d6eee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48770077"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="6f7e6-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="6f7e6-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6f7e6-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6f7e6-106">**Applies to:**</span></span>
- <span data-ttu-id="6f7e6-107">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="6f7e6-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="6f7e6-108">Каждая строка в таблице `DeviceTvmSecureConfigurationAssessment` содержит событие оценки для определенной настройки безопасности от функции [контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="6f7e6-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="6f7e6-109">Используйте этот справочник для проверки последних результатов оценки и определения соответствия устройства требованиям.</span><span class="sxs-lookup"><span data-stu-id="6f7e6-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="6f7e6-110">Сведения о других таблицах в схеме расширенной охоты см. в [справочнике по расширенной охоте](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="6f7e6-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6f7e6-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="6f7e6-111">Column name</span></span> | <span data-ttu-id="6f7e6-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6f7e6-112">Data type</span></span> | <span data-ttu-id="6f7e6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6f7e6-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="6f7e6-114">string</span><span class="sxs-lookup"><span data-stu-id="6f7e6-114">string</span></span> | <span data-ttu-id="6f7e6-115">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="6f7e6-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6f7e6-116">string</span><span class="sxs-lookup"><span data-stu-id="6f7e6-116">string</span></span> | <span data-ttu-id="6f7e6-117">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="6f7e6-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="6f7e6-118">string</span><span class="sxs-lookup"><span data-stu-id="6f7e6-118">string</span></span> | <span data-ttu-id="6f7e6-119">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="6f7e6-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="6f7e6-120">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="6f7e6-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="6f7e6-121">datetime</span><span class="sxs-lookup"><span data-stu-id="6f7e6-121">datetime</span></span> | <span data-ttu-id="6f7e6-122">Дата и время создания записи</span><span class="sxs-lookup"><span data-stu-id="6f7e6-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="6f7e6-123">string</span><span class="sxs-lookup"><span data-stu-id="6f7e6-123">string</span></span> | <span data-ttu-id="6f7e6-124">Уникальный идентификатор определенной настройки</span><span class="sxs-lookup"><span data-stu-id="6f7e6-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="6f7e6-125">string</span><span class="sxs-lookup"><span data-stu-id="6f7e6-125">string</span></span> | <span data-ttu-id="6f7e6-126">Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности</span><span class="sxs-lookup"><span data-stu-id="6f7e6-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="6f7e6-127">string</span><span class="sxs-lookup"><span data-stu-id="6f7e6-127">string</span></span> | <span data-ttu-id="6f7e6-128">Подкатегория или подгруппа, к которой относится настройка.</span><span class="sxs-lookup"><span data-stu-id="6f7e6-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="6f7e6-129">Во многих случаях здесь описываются конкретные возможности или функции.</span><span class="sxs-lookup"><span data-stu-id="6f7e6-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="6f7e6-130">string</span><span class="sxs-lookup"><span data-stu-id="6f7e6-130">string</span></span> | <span data-ttu-id="6f7e6-131">Оценка влияния настройки на общую оценку конфигурации (1–10)</span><span class="sxs-lookup"><span data-stu-id="6f7e6-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="6f7e6-132">boolean</span><span class="sxs-lookup"><span data-stu-id="6f7e6-132">boolean</span></span> | <span data-ttu-id="6f7e6-133">Указывает, правильно ли настроена конфигурация или политика</span><span class="sxs-lookup"><span data-stu-id="6f7e6-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="6f7e6-134">boolean</span><span class="sxs-lookup"><span data-stu-id="6f7e6-134">boolean</span></span> | <span data-ttu-id="6f7e6-135">Указывает, применяется ли конфигурация или политика к устройству.</span><span class="sxs-lookup"><span data-stu-id="6f7e6-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="6f7e6-136">string</span><span class="sxs-lookup"><span data-stu-id="6f7e6-136">string</span></span> | <span data-ttu-id="6f7e6-137">Дополнительные контекстные сведения о конфигурации или политике</span><span class="sxs-lookup"><span data-stu-id="6f7e6-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="6f7e6-138">boolean</span><span class="sxs-lookup"><span data-stu-id="6f7e6-138">boolean</span></span> | <span data-ttu-id="6f7e6-139">Указывает, будет ли оказывать влияние пользователь при применении конфигурации или политики</span><span class="sxs-lookup"><span data-stu-id="6f7e6-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6f7e6-140">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6f7e6-140">Related topics</span></span>

- [<span data-ttu-id="6f7e6-141">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="6f7e6-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6f7e6-142">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="6f7e6-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6f7e6-143">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="6f7e6-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6f7e6-144">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="6f7e6-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6f7e6-145">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="6f7e6-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6f7e6-146">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="6f7e6-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="6f7e6-147">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="6f7e6-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
