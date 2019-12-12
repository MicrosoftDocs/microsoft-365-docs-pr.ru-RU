---
title: Таблица DeviceTvmSecureConfigurationAssessment в схеме расширенной охоты
description: Сведения о событиях оценки безопасности функцией контроля угроз и уязвимостей в таблице DeviceTvmSecureConfigurationAssessment схемы расширенной охоты. Эти события предоставляют сведения о компьютере, а также сведения о настройке безопасности, влиянии и соответствии требованиям.
keywords: расширенная охота, охота на угрозы, охота на киберугрозы, поиск, запрос, телеметрия, ссылки на схему, kusto, таблица, столбец, тип данных, описание, контроль угроз и уязвимостей, TVM, управление устройствами, настройка безопасности, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 2fee44c0d9c9ff30ca23ccef863e056cadee7de8
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911508"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="be103-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="be103-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="be103-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="be103-106">**Applies to:**</span></span>
- <span data-ttu-id="be103-107">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="be103-107">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="be103-108">Каждая строка в таблице `DeviceTvmSecureConfigurationAssessment` содержит событие оценки для определенной настройки безопасности от функции [контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="be103-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="be103-109">Используйте этот справочник для проверки последних результатов оценки и определения соответствия устройства требованиям.</span><span class="sxs-lookup"><span data-stu-id="be103-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="be103-110">Сведения о других таблицах в схеме расширенной охоты см. в [справочнике по расширенной охоте](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="be103-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="be103-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="be103-111">Column name</span></span> | <span data-ttu-id="be103-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="be103-112">Data type</span></span> | <span data-ttu-id="be103-113">Описание</span><span class="sxs-lookup"><span data-stu-id="be103-113">Description</span></span> |
|-------------|-----------|-------------|
| `MachineId` | <span data-ttu-id="be103-114">string</span><span class="sxs-lookup"><span data-stu-id="be103-114">string</span></span> | <span data-ttu-id="be103-115">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="be103-115">Unique identifier for the machine in the service</span></span> |
| `ComputerName` | <span data-ttu-id="be103-116">string</span><span class="sxs-lookup"><span data-stu-id="be103-116">string</span></span> | <span data-ttu-id="be103-117">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="be103-117">Fully qualified domain name (FQDN) of the pool</span></span> |
| `OSPlatform` | <span data-ttu-id="be103-118">string</span><span class="sxs-lookup"><span data-stu-id="be103-118">string</span></span> | <span data-ttu-id="be103-119">Платформа операционной системы, используемой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="be103-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="be103-120">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="be103-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="be103-121">datetime</span><span class="sxs-lookup"><span data-stu-id="be103-121">dateTime</span></span> | <span data-ttu-id="be103-122">Дата и время создания записи</span><span class="sxs-lookup"><span data-stu-id="be103-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="be103-123">string</span><span class="sxs-lookup"><span data-stu-id="be103-123">string</span></span> | <span data-ttu-id="be103-124">Уникальный идентификатор определенной настройки</span><span class="sxs-lookup"><span data-stu-id="be103-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="be103-125">string</span><span class="sxs-lookup"><span data-stu-id="be103-125">string</span></span> | <span data-ttu-id="be103-126">Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности</span><span class="sxs-lookup"><span data-stu-id="be103-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="be103-127">string</span><span class="sxs-lookup"><span data-stu-id="be103-127">string</span></span> | <span data-ttu-id="be103-128">Подкатегория или подгруппа, к которой относится настройка.</span><span class="sxs-lookup"><span data-stu-id="be103-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="be103-129">Во многих случаях здесь описываются конкретные возможности или функции.</span><span class="sxs-lookup"><span data-stu-id="be103-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="be103-130">string</span><span class="sxs-lookup"><span data-stu-id="be103-130">string</span></span> | <span data-ttu-id="be103-131">Оценка влияния настройки на общую оценку конфигурации (1–10)</span><span class="sxs-lookup"><span data-stu-id="be103-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="be103-132">boolean</span><span class="sxs-lookup"><span data-stu-id="be103-132">boolean</span></span> | <span data-ttu-id="be103-133">Указывает, правильно ли настроена конфигурация или политика</span><span class="sxs-lookup"><span data-stu-id="be103-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="be103-134">См. также</span><span class="sxs-lookup"><span data-stu-id="be103-134">Related topics</span></span>

- [<span data-ttu-id="be103-135">Профилактическая охота на угрозы</span><span class="sxs-lookup"><span data-stu-id="be103-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="be103-136">Сведения о языке запросов</span><span class="sxs-lookup"><span data-stu-id="be103-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="be103-137">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="be103-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="be103-138">Охота на угрозы в электронной почте и устройствах</span><span class="sxs-lookup"><span data-stu-id="be103-138">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="be103-139">Общие сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="be103-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="be103-140">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="be103-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="be103-141">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="be103-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
