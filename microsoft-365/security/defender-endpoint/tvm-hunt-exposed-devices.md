---
title: Поиск представленных устройств
description: Узнайте, как управление угрозами и уязвимостью может использоваться для совместной работы администраторов безопасности, ИТ-администраторов и secOps.
keywords: сценарии mdatp-tvm, сценарии mdatp, tvm, tvm, снижение уязвимости & угрозы, снижение угрозы и уязвимости, улучшение конфигурации безопасности, увеличение показателей безопасности Microsoft для устройств, повышение & уязвимости Microsoft Secure Score для устройств, Microsoft Secure Score для устройств, оценка экспозиции, средства управления безопасностью
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 99e59005bc01a113567e64c921ddcdc1d66785d2
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408295"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a><span data-ttu-id="3a46e-104">Hunt for exposed devices - threat and vulnerability management</span><span class="sxs-lookup"><span data-stu-id="3a46e-104">Hunt for exposed devices - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3a46e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3a46e-105">**Applies to:**</span></span>

- [<span data-ttu-id="3a46e-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3a46e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3a46e-107">Управление угрозами и уязвимостями</span><span class="sxs-lookup"><span data-stu-id="3a46e-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3a46e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3a46e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3a46e-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="3a46e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3a46e-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="3a46e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a><span data-ttu-id="3a46e-111">Использование расширенных средств охоты для поиска устройств с уязвимостями</span><span class="sxs-lookup"><span data-stu-id="3a46e-111">Use advanced hunting to find devices with vulnerabilities</span></span>

<span data-ttu-id="3a46e-112">Расширенное выслеживание— это средство для выслеживания угроз на основе запросов, которое позволяет изучать необработанные данные за период до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="3a46e-112">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="3a46e-113">Вы можете упреждающий осмотр событий в сети, чтобы найти индикаторы и объекты угрозы.</span><span class="sxs-lookup"><span data-stu-id="3a46e-113">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="3a46e-114">Гибкий доступ к данным позволяет безудержно искать как известные, так и потенциальные угрозы.</span><span class="sxs-lookup"><span data-stu-id="3a46e-114">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span> [<span data-ttu-id="3a46e-115">Дополнительные дополнительные информацию о продвинутой охоте</span><span class="sxs-lookup"><span data-stu-id="3a46e-115">Learn more about advanced hunting</span></span>](advanced-hunting-overview.md)

### <a name="schema-tables"></a><span data-ttu-id="3a46e-116">Таблицы схем</span><span class="sxs-lookup"><span data-stu-id="3a46e-116">Schema tables</span></span>

- <span data-ttu-id="3a46e-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) — инвентаризация программного обеспечения, установленного на устройствах, включая сведения о версии и состояние конечной поддержки.</span><span class="sxs-lookup"><span data-stu-id="3a46e-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventory of software installed on devices, including their version information and end-of-support status.</span></span>

- <span data-ttu-id="3a46e-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) — уязвимости программного обеспечения, найденные на устройствах, и список доступных обновлений безопасности, которые могут быть доступны для каждой уязвимости.</span><span class="sxs-lookup"><span data-stu-id="3a46e-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Software vulnerabilities found on devices and the list of available security updates that address each vulnerability.</span></span>

- <span data-ttu-id="3a46e-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) — база знаний об открытых уязвимостях, в том числе о том, доступен ли код эксплойта.</span><span class="sxs-lookup"><span data-stu-id="3a46e-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available.</span></span>

- <span data-ttu-id="3a46e-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) — события оценки угроз и уязвимостей, указывающие на состояние различных конфигураций безопасности на устройствах.</span><span class="sxs-lookup"><span data-stu-id="3a46e-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Threat and vulnerability management assessment events, indicating the status of various security configurations on devices.</span></span>

- <span data-ttu-id="3a46e-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) — база знаний о различных конфигурациях безопасности, используемых управлением & уязвимостей для оценки устройств; включает сопоставления с различными стандартами и эталонами</span><span class="sxs-lookup"><span data-stu-id="3a46e-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a><span data-ttu-id="3a46e-122">Проверьте, какие устройства участвуют в оповещениях высокой степени тяжести</span><span class="sxs-lookup"><span data-stu-id="3a46e-122">Check which devices are involved in high severity alerts</span></span>

1. <span data-ttu-id="3a46e-123">Перейдите **к продвинутой охоте** с левой области навигации Центра безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="3a46e-123">Go to **Advanced hunting** from the left-hand navigation pane of the Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="3a46e-124">Прокрутите до расширенных схем охоты TVM, чтобы ознакомиться с именами столбцов.</span><span class="sxs-lookup"><span data-stu-id="3a46e-124">Scroll down to the TVM advanced hunting schemas to familiarize yourself with the column names.</span></span>

3. <span data-ttu-id="3a46e-125">Введите следующие запросы:</span><span class="sxs-lookup"><span data-stu-id="3a46e-125">Enter the following queries:</span></span>

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId
| join kind =inner(DeviceAlertEvents) on DeviceId  
| summarize NumOfVulnerabilities=any(NumOfVulnerabilities),
DeviceName=any(DeviceName) by DeviceId, AlertId
| project DeviceName, NumOfVulnerabilities, AlertId  
| order by NumOfVulnerabilities desc
```

## <a name="related-topics"></a><span data-ttu-id="3a46e-126">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3a46e-126">Related topics</span></span>

- [<span data-ttu-id="3a46e-127">Обзор управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="3a46e-127">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3a46e-128">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="3a46e-128">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="3a46e-129">Интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="3a46e-129">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)
- [<span data-ttu-id="3a46e-130">Настройка доступа к данным для ролей управления угрозами и уязвимостями</span><span class="sxs-lookup"><span data-stu-id="3a46e-130">Configure data access for threat and vulnerability management roles</span></span>](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [<span data-ttu-id="3a46e-131">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="3a46e-131">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [<span data-ttu-id="3a46e-132">Все расширенные таблицы охоты</span><span class="sxs-lookup"><span data-stu-id="3a46e-132">All advanced hunting tables</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
