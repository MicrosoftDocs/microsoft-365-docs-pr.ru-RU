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
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075542"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Таблица в продвинутой схеме охоты содержит инвентаризацию программного обеспечения управления & уязвимостей, установленного в настоящее время на устройствах в вашей сети, включая конечные сведения `DeviceTvmSoftwareInventory` о поддержке. [](next-gen-threat-and-vuln-mgt.md) Например, можно искать события, связанные с устройствами, установленными с уязвимой в настоящее время версией программного обеспечения. Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

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
| `EndOfSupportStatus` | string | Указывает этап жизненного цикла программного продукта относительно указанной даты окончания поддержки (EOS) или даты окончания срока службы (EOL). |
| `EndOfSupportDate` | строка | Дата окончания службы поддержки (EOS) или даты окончания срока службы программного продукта |



## <a name="related-topics"></a>Статьи по теме

- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
- [Обзор контроля угроз и уязвимостей](next-gen-threat-and-vuln-mgt.md)

