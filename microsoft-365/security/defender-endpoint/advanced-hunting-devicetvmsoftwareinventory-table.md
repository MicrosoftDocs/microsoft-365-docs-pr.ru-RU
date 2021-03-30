---
title: DeviceTvmSoftwareInventory table in the advanced hunting schema
description: Узнайте о инвентаризации программного обеспечения на устройствах в таблице DeviceTvmSoftwareInventory продвинутой схемы охоты.
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
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408627"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Таблица в продвинутой схеме охоты содержит инвентаризацию программного обеспечения для управления угрозами и уязвимостями, установленного в настоящее время на устройствах в сети, включая конец сведений `DeviceTvmSoftwareInventory` о поддержке. [](next-gen-threat-and-vuln-mgt.md) Например, можно искать события, связанные с устройствами, установленными с уязвимой в настоящее время версией программного обеспечения. Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

DeviceTVMSoftwareInventory содержит все программное обеспечение, которое управление угрозами и уязвимостью было в состоянии соответствовать общему переумывке платформы (CPE) — является ли оно уязвимым или нет.

>[!NOTE]
>Таблицы `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` и таблицы заменили `DeviceTvmSoftwareInventoryVulnerabilities` таблицу. В первых двух таблицах содержится больше столбцов, которые можно использовать для информирования о действиях по управлению уязвимостями.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `DeviceId` | string | Уникальный идентификатор устройства в службе. |
| `DeviceName` | Строка | Полное доменное имя (FQDN) устройства. |
| `OSPlatform` | Строка | Платформа операционной системы, запущенной на устройстве. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7. |
| `OSVersion` | string | Версия операционной системы, запущенной на устройстве. |
| `OSArchitecture` | Строка | Архитектура операционной системы, запущенной на устройстве. |
| `SoftwareVendor` | Строка | Имя поставщика программного обеспечения. |
| `SoftwareName` | Строка | Имя программного продукта. |
| `SoftwareVersion` | Строка | Номер версии программного продукта. |
| `EndOfSupportStatus` | Строка | Указывает этап жизненного цикла программного продукта относительно указанной даты окончания службы поддержки (EOS) или даты окончания срока службы (EOL). |
| `EndOfSupportDate` | Строка | Дата окончания службы поддержки (EOS) или дата окончания срока службы программного продукта. |

## <a name="related-topics"></a>Статьи по теме

- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
- [Обзор контроля угроз и уязвимостей](next-gen-threat-and-vuln-mgt.md)
