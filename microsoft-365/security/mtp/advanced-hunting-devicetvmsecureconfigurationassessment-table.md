---
title: Таблица DeviceTvmSecureConfigurationAssessment в схеме расширенной охоты
description: Сведения о событиях оценки безопасности функцией контроля угроз и уязвимостей в таблице DeviceTvmSecureConfigurationAssessment схемы расширенной охоты. Эти события предоставляют сведения о компьютере, а также сведения о настройке безопасности, влиянии и соответствии требованиям.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b186574cfc1307dfd8a01f7a77ef60bf91f4b162
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197001"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="5153a-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="5153a-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5153a-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5153a-106">**Applies to:**</span></span>
- <span data-ttu-id="5153a-107">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="5153a-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="5153a-108">Каждая строка в таблице `DeviceTvmSecureConfigurationAssessment` содержит событие оценки для определенной настройки безопасности от функции [контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="5153a-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="5153a-109">Используйте этот справочник для проверки последних результатов оценки и определения соответствия устройства требованиям.</span><span class="sxs-lookup"><span data-stu-id="5153a-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="5153a-110">Сведения о других таблицах в схеме расширенной охоты см. в [справочнике по расширенной охоте](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="5153a-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5153a-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="5153a-111">Column name</span></span> | <span data-ttu-id="5153a-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="5153a-112">Data type</span></span> | <span data-ttu-id="5153a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5153a-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="5153a-114">string</span><span class="sxs-lookup"><span data-stu-id="5153a-114">string</span></span> | <span data-ttu-id="5153a-115">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="5153a-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5153a-116">string</span><span class="sxs-lookup"><span data-stu-id="5153a-116">string</span></span> | <span data-ttu-id="5153a-117">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="5153a-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="5153a-118">string</span><span class="sxs-lookup"><span data-stu-id="5153a-118">string</span></span> | <span data-ttu-id="5153a-119">Платформа операционной системы, используемой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5153a-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="5153a-120">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="5153a-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="5153a-121">datetime</span><span class="sxs-lookup"><span data-stu-id="5153a-121">datetime</span></span> | <span data-ttu-id="5153a-122">Дата и время создания записи</span><span class="sxs-lookup"><span data-stu-id="5153a-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="5153a-123">string</span><span class="sxs-lookup"><span data-stu-id="5153a-123">string</span></span> | <span data-ttu-id="5153a-124">Уникальный идентификатор определенной настройки</span><span class="sxs-lookup"><span data-stu-id="5153a-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="5153a-125">string</span><span class="sxs-lookup"><span data-stu-id="5153a-125">string</span></span> | <span data-ttu-id="5153a-126">Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности</span><span class="sxs-lookup"><span data-stu-id="5153a-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="5153a-127">string</span><span class="sxs-lookup"><span data-stu-id="5153a-127">string</span></span> | <span data-ttu-id="5153a-128">Подкатегория или подгруппа, к которой относится настройка.</span><span class="sxs-lookup"><span data-stu-id="5153a-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="5153a-129">Во многих случаях здесь описываются конкретные возможности или функции.</span><span class="sxs-lookup"><span data-stu-id="5153a-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="5153a-130">string</span><span class="sxs-lookup"><span data-stu-id="5153a-130">string</span></span> | <span data-ttu-id="5153a-131">Оценка влияния настройки на общую оценку конфигурации (1–10)</span><span class="sxs-lookup"><span data-stu-id="5153a-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="5153a-132">boolean</span><span class="sxs-lookup"><span data-stu-id="5153a-132">boolean</span></span> | <span data-ttu-id="5153a-133">Указывает, правильно ли настроена конфигурация или политика</span><span class="sxs-lookup"><span data-stu-id="5153a-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5153a-134">См. также</span><span class="sxs-lookup"><span data-stu-id="5153a-134">Related topics</span></span>

- [<span data-ttu-id="5153a-135">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="5153a-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5153a-136">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="5153a-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5153a-137">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="5153a-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5153a-138">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="5153a-138">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5153a-139">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="5153a-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5153a-140">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="5153a-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="5153a-141">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="5153a-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
