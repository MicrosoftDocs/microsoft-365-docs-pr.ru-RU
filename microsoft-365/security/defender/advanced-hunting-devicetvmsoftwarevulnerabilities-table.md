---
title: Таблица DeviceTvmSoftwareVulnerabilities в продвинутой схеме охоты
description: Узнайте об уязвимостях программного обеспечения, найденных на устройствах, и списке доступных обновлений безопасности, которые будут рассматривать каждую уязвимость в таблице DeviceTvmSoftwareVulnerabilities продвинутой схемы охоты.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 24da8f556fe9f8a3b8172afe87ea9a87e4522d44
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934829"
---
# <a name="devicetvmsoftwarevulnerabilities"></a>DeviceTvmSoftwareVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

>[!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

Таблица в продвинутой схеме охоты содержит список уязвимостей управления & уязвимостей в `DeviceTvmSoftwareVulnerabilities` установленных программных [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) продуктах. Эта таблица также содержит сведения об операционной системе, ИД CVE и сведения о серьезности уязвимости. Например, эту таблицу можно использовать для охоты на события, связанные с устройствами с серьезными уязвимостями в программном обеспечении. Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

>[!NOTE]
> Таблицы `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` и таблицы заменили `DeviceTvmSoftwareInventoryVulnerabilities` таблицу. В первых двух таблицах содержится больше столбцов, которые можно использовать для информирования о действиях по управлению уязвимыми группами или для охоты за уязвимыми устройствами.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `OSPlatform` | string | Платформа операционной системы, используемой на компьютере. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7. |
| `OSVersion` | string | Версия операционной системы, используемой на компьютере |
| `OSArchitecture` | string | Архитектура операционной системы, используемой на компьютере |
| `SoftwareVendor` | string | Имя поставщика программного обеспечения |
| `SoftwareName` | string | Название программного продукта |
| `SoftwareVersion` | string | Номер версии программного продукта |
| `CveId` | string | Уникальный идентификатор, назначенный уязвимости в системе общеизвестных уязвимостей и рисков (CVE) |
| `VulnerabilitySeverityLevel` | string | Уровень серьезности, назначенный уязвимости безопасности на основе оценки CVSS и динамических коэффициентов, на которые влияет обстановка с угрозами |
| `RecommendedSecurityUpdate` | string | Имя или описание обновления безопасности, предоставляемого поставщиком программного обеспечения для устранения уязвимости |
| `RecommendedSecurityUpdateId` | Строка | Идентификатор применимых обновлений или идентификаторов безопасности для соответствующих статей руководства или базы знаний (KB). |



## <a name="related-topics"></a>Статьи по теме

- [Заблаговременный поиск угроз](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
- [Обзор контроля угроз и уязвимостей](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)