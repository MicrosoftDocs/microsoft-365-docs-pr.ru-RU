---
title: Таблица DeviceTvmSecureConfigurationAssessment в схеме расширенной охоты
description: Узнайте о событиях & управления безопасностью управления угрозами в таблице DeviceTvmSecureConfigurationAssessment схемы advanced hunting. Эти события предоставляют сведения о устройстве, а также сведения о конфигурации безопасности, влияние и соответствие требованиям.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075046"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="7d090-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="7d090-105">DeviceTvmSecureConfigurationAssessment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7d090-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7d090-106">**Applies to:**</span></span>
- [<span data-ttu-id="7d090-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7d090-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="7d090-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7d090-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7d090-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7d090-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="7d090-110">Каждая строка в таблице `DeviceTvmSecureConfigurationAssessment` содержит событие оценки для определенной настройки безопасности от функции [контроля угроз и уязвимостей](next-gen-threat-and-vuln-mgt.md).</span><span class="sxs-lookup"><span data-stu-id="7d090-110">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="7d090-111">Используйте этот справочник для проверки последних результатов оценки и определения соответствия устройства требованиям.</span><span class="sxs-lookup"><span data-stu-id="7d090-111">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="7d090-112">Сведения о других таблицах в схеме расширенной охоты см. в [справочнике по расширенной охоте](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="7d090-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="7d090-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="7d090-113">Column name</span></span> | <span data-ttu-id="7d090-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7d090-114">Data type</span></span> | <span data-ttu-id="7d090-115">Описание</span><span class="sxs-lookup"><span data-stu-id="7d090-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="7d090-116">string</span><span class="sxs-lookup"><span data-stu-id="7d090-116">string</span></span> | <span data-ttu-id="7d090-117">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="7d090-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="7d090-118">строка</span><span class="sxs-lookup"><span data-stu-id="7d090-118">string</span></span> | <span data-ttu-id="7d090-119">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="7d090-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="7d090-120">строка</span><span class="sxs-lookup"><span data-stu-id="7d090-120">string</span></span> | <span data-ttu-id="7d090-121">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="7d090-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="7d090-122">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="7d090-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="7d090-123">datetime</span><span class="sxs-lookup"><span data-stu-id="7d090-123">datetime</span></span> |<span data-ttu-id="7d090-124">Дата и время создания записи</span><span class="sxs-lookup"><span data-stu-id="7d090-124">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="7d090-125">string</span><span class="sxs-lookup"><span data-stu-id="7d090-125">string</span></span> | <span data-ttu-id="7d090-126">Уникальный идентификатор определенной настройки</span><span class="sxs-lookup"><span data-stu-id="7d090-126">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="7d090-127">string</span><span class="sxs-lookup"><span data-stu-id="7d090-127">string</span></span> | <span data-ttu-id="7d090-128">Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности</span><span class="sxs-lookup"><span data-stu-id="7d090-128">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="7d090-129">string</span><span class="sxs-lookup"><span data-stu-id="7d090-129">string</span></span> |<span data-ttu-id="7d090-130">Подкатегория или подгруппа, к которой относится настройка.</span><span class="sxs-lookup"><span data-stu-id="7d090-130">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="7d090-131">Во многих случаях здесь описываются конкретные возможности или функции.</span><span class="sxs-lookup"><span data-stu-id="7d090-131">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="7d090-132">string</span><span class="sxs-lookup"><span data-stu-id="7d090-132">string</span></span> | <span data-ttu-id="7d090-133">Оценка влияния настройки на общую оценку конфигурации (1–10)</span><span class="sxs-lookup"><span data-stu-id="7d090-133">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="7d090-134">boolean</span><span class="sxs-lookup"><span data-stu-id="7d090-134">boolean</span></span> | <span data-ttu-id="7d090-135">Указывает, правильно ли настроена конфигурация или политика</span><span class="sxs-lookup"><span data-stu-id="7d090-135">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="7d090-136">boolean</span><span class="sxs-lookup"><span data-stu-id="7d090-136">boolean</span></span> | <span data-ttu-id="7d090-137">Указывает, применима ли конфигурация или политика к устройству</span><span class="sxs-lookup"><span data-stu-id="7d090-137">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="7d090-138">строка</span><span class="sxs-lookup"><span data-stu-id="7d090-138">string</span></span> | <span data-ttu-id="7d090-139">Дополнительные контекстные сведения о конфигурации или политике</span><span class="sxs-lookup"><span data-stu-id="7d090-139">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="7d090-140">boolean</span><span class="sxs-lookup"><span data-stu-id="7d090-140">boolean</span></span> | <span data-ttu-id="7d090-141">Указывает, будет ли влияние пользователя, если применяется конфигурация или политика</span><span class="sxs-lookup"><span data-stu-id="7d090-141">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7d090-142">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7d090-142">Related topics</span></span>

- [<span data-ttu-id="7d090-143">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="7d090-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7d090-144">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="7d090-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7d090-145">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="7d090-145">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="7d090-146">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="7d090-146">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)