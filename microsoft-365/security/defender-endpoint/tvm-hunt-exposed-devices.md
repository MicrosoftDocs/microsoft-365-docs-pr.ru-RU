---
title: Охота на выставленные устройства
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
ms.openlocfilehash: 9af7464d9cae06dc53abb019aa0b189d6e72e749
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068992"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a>Hunt for exposed devices - threat and vulnerability management

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Управление угрозами и уязвимостями](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a>Использование расширенных средств охоты для поиска устройств с уязвимостями

Расширенное выслеживание— это средство для выслеживания угроз на основе запросов, которое позволяет изучать необработанные данные за период до 30 дней. Вы можете упреждающий осмотр событий в сети, чтобы найти индикаторы и объекты угрозы. Гибкий доступ к данным позволяет безудержно искать как известные, так и потенциальные угрозы. [Дополнительные дополнительные информацию о продвинутой охоте](advanced-hunting-overview.md)

### <a name="schema-tables"></a>Таблицы схем

- [DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) — инвентаризация программного обеспечения, установленного на устройствах, включая сведения о версии и состояние конечной поддержки

- [DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) — уязвимости программного обеспечения, найденные на устройствах, и список доступных обновлений безопасности, которые могут быть доступны для каждой уязвимости.

- [DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) — база знаний об открытых уязвимостях, включая общедоступный код эксплойта

- [DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) — события оценки угроз и уязвимостей, указывающие на состояние различных конфигураций безопасности на устройствах.

- [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) — база знаний о различных конфигурациях безопасности, используемых управлением & уязвимостей для оценки устройств; включает сопоставления с различными стандартами и эталонами

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a>Проверьте, какие устройства участвуют в оповещениях высокой степени тяжести

1. Перейдите **к продвинутой охоте** с левой области навигации Центра безопасности Microsoft Defender.

2. Прокрутите до расширенных схем охоты TVM, чтобы ознакомиться с именами столбцов.

3. Введите следующие запросы:

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

## <a name="related-topics"></a>Статьи по теме

- [Обзор управления угрозами и уязвимостью](next-gen-threat-and-vuln-mgt.md)
- [Рекомендации по безопасности](tvm-security-recommendation.md)
- [Интерфейсы API](next-gen-threat-and-vuln-mgt.md#apis)
- [Настройка доступа к данным для ролей управления угрозами и уязвимостями](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [Обзор расширенной охоты на угрозы](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Все расширенные таблицы охоты](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
