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
ms.openlocfilehash: d03b278fbf029b08b476f20292315807a3f5e32a
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808624"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="2143a-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="2143a-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="2143a-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2143a-106">**Applies to:**</span></span>
- <span data-ttu-id="2143a-107">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="2143a-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="2143a-108">Каждая строка в таблице `DeviceTvmSecureConfigurationAssessment` содержит событие оценки для определенной настройки безопасности от функции [контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="2143a-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="2143a-109">Используйте этот справочник для проверки последних результатов оценки и определения соответствия устройства требованиям.</span><span class="sxs-lookup"><span data-stu-id="2143a-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="2143a-110">Сведения о других таблицах в схеме расширенной охоты см. в [справочнике по расширенной охоте](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2143a-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2143a-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="2143a-111">Column name</span></span> | <span data-ttu-id="2143a-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2143a-112">Data type</span></span> | <span data-ttu-id="2143a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2143a-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="2143a-114">string</span><span class="sxs-lookup"><span data-stu-id="2143a-114">string</span></span> | <span data-ttu-id="2143a-115">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="2143a-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2143a-116">string</span><span class="sxs-lookup"><span data-stu-id="2143a-116">string</span></span> | <span data-ttu-id="2143a-117">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="2143a-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="2143a-118">string</span><span class="sxs-lookup"><span data-stu-id="2143a-118">string</span></span> | <span data-ttu-id="2143a-119">Платформа операционной системы, используемой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2143a-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="2143a-120">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2143a-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="2143a-121">datetime</span><span class="sxs-lookup"><span data-stu-id="2143a-121">datetime</span></span> | <span data-ttu-id="2143a-122">Дата и время создания записи</span><span class="sxs-lookup"><span data-stu-id="2143a-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="2143a-123">string</span><span class="sxs-lookup"><span data-stu-id="2143a-123">string</span></span> | <span data-ttu-id="2143a-124">Уникальный идентификатор определенной настройки</span><span class="sxs-lookup"><span data-stu-id="2143a-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="2143a-125">string</span><span class="sxs-lookup"><span data-stu-id="2143a-125">string</span></span> | <span data-ttu-id="2143a-126">Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности</span><span class="sxs-lookup"><span data-stu-id="2143a-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="2143a-127">string</span><span class="sxs-lookup"><span data-stu-id="2143a-127">string</span></span> | <span data-ttu-id="2143a-128">Подкатегория или подгруппа, к которой относится настройка.</span><span class="sxs-lookup"><span data-stu-id="2143a-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="2143a-129">Во многих случаях здесь описываются конкретные возможности или функции.</span><span class="sxs-lookup"><span data-stu-id="2143a-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="2143a-130">string</span><span class="sxs-lookup"><span data-stu-id="2143a-130">string</span></span> | <span data-ttu-id="2143a-131">Оценка влияния настройки на общую оценку конфигурации (1–10)</span><span class="sxs-lookup"><span data-stu-id="2143a-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="2143a-132">boolean</span><span class="sxs-lookup"><span data-stu-id="2143a-132">boolean</span></span> | <span data-ttu-id="2143a-133">Указывает, правильно ли настроена конфигурация или политика</span><span class="sxs-lookup"><span data-stu-id="2143a-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2143a-134">См. также</span><span class="sxs-lookup"><span data-stu-id="2143a-134">Related topics</span></span>

- [<span data-ttu-id="2143a-135">Профилактическая охота на угрозы</span><span class="sxs-lookup"><span data-stu-id="2143a-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2143a-136">Сведения о языке запросов</span><span class="sxs-lookup"><span data-stu-id="2143a-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2143a-137">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="2143a-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2143a-138">Охота на угрозы в электронной почте и устройствах</span><span class="sxs-lookup"><span data-stu-id="2143a-138">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2143a-139">Общие сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="2143a-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2143a-140">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="2143a-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="2143a-141">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="2143a-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
