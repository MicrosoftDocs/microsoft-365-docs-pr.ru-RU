---
title: Таблица DeviceTvmSoftwareVulnerabilities в продвинутой схеме охоты
description: Узнайте об уязвимостях программного обеспечения, найденных на устройствах, и списке доступных обновлений безопасности, которые будут рассматривать каждую уязвимость в таблице DeviceTvmSoftwareVulnerabilities продвинутой схемы охоты.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b38297cd0fa2e931619ff9c0557d2ae868c7aa4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076037"
---
# <a name="devicetvmsoftwarevulnerabilities"></a>DeviceTvmSoftwareVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Таблица в продвинутой схеме охоты содержит список уязвимостей управления & уязвимостей в `DeviceTvmSoftwareVulnerabilities` установленных программных [](next-gen-threat-and-vuln-mgt.md) продуктах. Эта таблица также содержит сведения об операционной системе, ИД CVE и сведения о серьезности уязвимости. Например, эту таблицу можно использовать для охоты на события, связанные с устройствами с серьезными уязвимостями в программном обеспечении. Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

>[!NOTE]
>Таблицы `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` и таблицы заменили `DeviceTvmSoftwareInventoryVulnerabilities` таблицу. В первых двух таблицах содержится больше столбцов, которые можно использовать для информирования о действиях по управлению уязвимостями.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `DeviceId` | string | Уникальный идентификатор устройства в службе |
| `DeviceName` | строка | Полное доменное имя (FQDN) устройства |
| `OSPlatform` | строка | Платформа операционной системы, запущенной на устройстве. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7. |
| `OSVersion` | string | Версия операционной системы, запущенной на устройстве |
| `OSArchitecture` | строка | Архитектура операционной системы, запущенной на устройстве |
| `SoftwareVendor` | строка | Имя поставщика программного обеспечения |
| `SoftwareName` | string | Название программного продукта |
| `SoftwareVersion` | string | Номер версии программного продукта |
| `CveId` | string | Уникальный идентификатор, назначенный уязвимости в системе общеизвестных уязвимостей и рисков (CVE) |
| `VulnerabilitySeverityLevel` | string | Уровень серьезности, назначенный уязвимости безопасности на основе оценки CVSS и динамических коэффициентов, на которые влияет обстановка с угрозами |
| `RecommendedSecurityUpdate` | string | Имя или описание обновления безопасности, предоставляемого поставщиком программного обеспечения для устранения уязвимости |
| `RecommendedSecurityUpdateId` | строка | Идентификатор применимых обновлений или идентификаторов безопасности для соответствующих статей руководства или базы знаний (KB). |



## <a name="related-topics"></a>Статьи по теме

- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
- [Обзор контроля угроз и уязвимостей](next-gen-threat-and-vuln-mgt.md)
