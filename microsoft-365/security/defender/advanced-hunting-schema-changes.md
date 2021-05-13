---
title: Изменение имен в схеме Microsoft 365 Defender
description: Отслеживание и проверка именования изменений таблиц и столбцов в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, ссылка схемы, кусто, таблица, данные, изменения имен, переименование
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
ms.openlocfilehash: a387892dde0fbe96e4a523b2247448a3c7e374b8
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470500"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Advanced hunting schema - Naming changes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Передовая схема охоты](advanced-hunting-schema-tables.md) регулярно обновляется, чтобы добавлять новые таблицы и столбцы. В некоторых случаях имена существующих столбцов переименовываются или заменяются для улучшения пользовательского интерфейса. Обратитесь к этой статье, чтобы просмотреть изменения именования, которые могут повлиять на запросы.

Изменения именования автоматически применяются к запросам, сохраненным в центре безопасности, включая запросы, используемые пользовательскими правилами обнаружения. Не нужно обновлять эти запросы вручную. Однако необходимо обновить следующие запросы:
- Запросы, которые запускаются с помощью API
- Запросы, сохраненные в другом месте за пределами центра безопасности

## <a name="december-2020"></a>Декабрь 2020 г.

| Имя таблицы | Исходное имя столбца | Новое имя столбца | Причина изменений
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | Отзывы пользователей |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | Отзывы пользователей |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | Отзывы пользователей |

## <a name="january-2021"></a>Январь 2021 г.

| Имя столбца | Имя исходного значения | Новое имя значения | Причина изменений
|--|--|--|--|
| `DetectionSource` | MCAS |    Microsoft Cloud App Security | Ребрендинг |
| `DetectionSource` | WindowsDefenderAtp|   EDR| Ребрендинг |
| `DetectionSource` | WindowsDefenderAv | Защита от вирусов | Ребрендинг |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | Ребрендинг |
| `DetectionSource` | CustomerTI |  Настраиваемый TI | Ребрендинг |
| `DetectionSource` | OfficeATP | Microsoft Defender для Office 365 | Ребрендинг |
| `DetectionSource` | MTP   | Microsoft 365 Defender | Ребрендинг |
| `DetectionSource` | AzureATP |    Microsoft Defender для удостоверений | Ребрендинг |
| `DetectionSource` | CustomDetection   | Настраиваемый обнаружение | Ребрендинг |
| `DetectionSource` | Автоматическаяинвестигация |Автоматическое расследование | Ребрендинг |
| `DetectionSource` | ThreatExperts | Эксперты Майкрософт по угрозам | Ребрендинг |
| `DetectionSource` | TI третьей стороны | Датчики 3-й стороны | Ребрендинг |
| `ServiceSource` | ATP в Защитнике Windows| Microsoft Defender для конечной точки | Ребрендинг |
|`ServiceSource` |Защита от угроз (Майкрософт)   | Microsoft 365 Defender | Ребрендинг |
| `ServiceSource` | Office 365 ATP  |Microsoft Defender для Office 365 | Ребрендинг |
| `ServiceSource` |Azure ATP    |Microsoft Defender для удостоверений | Ребрендинг |

`DetectionSource`доступна в таблице [AlertInfo.](advanced-hunting-alertinfo-table.md) `ServiceSource`доступно в [таблицах AlertEvidence](advanced-hunting-alertevidence-table.md) и [AlertInfo.](advanced-hunting-alertinfo-table.md) 

## <a name="february-2021"></a>Февраль 2021 г.

1. В [таблицах EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) и [EmailEvents](advanced-hunting-emailevents-table.md) столбцы и столбцы `MalwareFilterVerdict` `PhishFilterVerdict` заменены `ThreatTypes` столбцом. Столбцы `MalwareDetectionMethod` `PhishDetectionMethod` и столбцы также были заменены `DetectionMethods` столбцом. Эта оптимизация позволяет нам предоставлять дополнительные сведения в новых столбцах. Сопоставление приведено ниже.

    | Имя таблицы | Исходное имя столбца | Новое имя столбца | Причина изменений
    |--|--|--|--|
    | `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Включай дополнительные методы обнаружения |
    | `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Включаем дополнительные типы угроз |
    | `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Включай дополнительные методы обнаружения |
    | `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Включаем дополнительные типы угроз |


2. В `EmailAttachmentInfo` таблицах `EmailEvents` и таблицах `ThreatNames` столбец был добавлен, чтобы предоставить дополнительные сведения об угрозе электронной почты. В этом столбце содержатся такие значения, как спам или фишинг.

3. В таблице [DeviceInfo](advanced-hunting-deviceinfo-table.md) столбец был заменен столбцом `DeviceObjectId` на основе `AadDeviceId` отзывов клиентов.

4. В таблице [DeviceEvents](advanced-hunting-deviceevents-table.md) несколько имен ActionType были изменены, чтобы лучше отражать описание действия. Подробные сведения об изменениях приведены ниже.

    | Имя таблицы | Исходное имя ActionType | Новое имя ActionType | Причина изменений
    |--|--|--|--|
    | `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | Отзывы пользователей |
    | `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | Отзывы пользователей |
    | `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | Отзывы пользователей |
    | `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | Отзывы пользователей |

## <a name="march-2021"></a>Март 2021 г.

Таблица `DeviceTvmSoftwareInventoryVulnerabilities` обесценилась. Его заменяют `DeviceTvmSoftwareInventory` таблицы `DeviceTvmSoftwareVulnerabilities` и таблицы.

## <a name="may-2021"></a>Май 2021 г.

Таблица `AppFileEvents` обесценилась. В таблице содержатся сведения, которые раньше были в таблице, а также другие действия `CloudAppEvents` `AppFileEvents` в облачных службах.

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)