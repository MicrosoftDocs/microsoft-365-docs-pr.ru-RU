---
title: Изменения именования в схеме предварительной охоты Microsoft 365 Defender
description: Отслеживание и проверка именования изменений таблиц и столбцов в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, data, naming changes, rename, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: cd06286083297d0930270868b99a14f8ddb2f4b2
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461671"
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
| `DetectionSource` | ThreatExperts | Microsoft Threat Experts | Ребрендинг |
| `DetectionSource` | TI третьей стороны | Датчики 3-й стороны | Ребрендинг |
| `ServiceSource` | ATP в Microsoft Defender — это| Microsoft Defender для конечной точки | Ребрендинг |
|`ServiceSource` |Защита от угроз (Майкрософт)   | Microsoft 365 Defender | Ребрендинг |
| `ServiceSource` | Office 365 ATP  |Microsoft Defender для Office 365 | Ребрендинг |
| `ServiceSource` |Azure ATP    |Microsoft Defender для удостоверений | Ребрендинг |

`DetectionSource`доступна в таблице [AlertInfo.](advanced-hunting-alertinfo-table.md) `ServiceSource`доступно в [таблицах AlertEvidence](advanced-hunting-alertevidence-table.md) и [AlertInfo.](advanced-hunting-alertinfo-table.md) 

## <a name="february-2021"></a>Февраль 2021 г.

1. В [таблицах EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) и [EmailEvents](advanced-hunting-emailevents-table.md) мы обесценили столбцы и заменили `MalwareFilterVerdict` их `PhishFilterVerdict` `ThreatTypes` столбцом. Кроме того, мы сместили `MalwareDetectionMethod` столбцы и `PhishDetectionMethod` столбцы и заменили их `DetectionMethods` столбцом. Эта оптимизация позволяет нам предоставлять дополнительные сведения в новых столбцах. Сопоставление приведено ниже.

| Имя таблицы | Исходное имя столбца | Новое имя столбца | Причина изменений
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Включай дополнительные методы обнаружения |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Включаем дополнительные типы угроз |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Включай дополнительные методы обнаружения |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Включаем дополнительные типы угроз |


2. В `EmailAttachmentInfo` таблицах `EmailEvents` и таблицах мы добавили столбец, `ThreatNames` чтобы предоставить дополнительные сведения об угрозе электронной почты. В этом столбце содержатся такие значения, как спам или фишинг.

3. В таблице [DeviceInfo](advanced-hunting-deviceinfo-table.md) мы заменили столбец на `DeviceObjectId` основе `AadDeviceId` отзывов клиентов.

4. В таблице [DeviceEvents](advanced-hunting-deviceevents-table.md) мы обновили несколько имен ActionType, чтобы лучше отражать описание действия. Подробные сведения можно найти ниже.

| Имя таблицы | Исходное имя ActionType | Новое имя ActionType | Причина изменений
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | Отзывы пользователей |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | Отзывы пользователей |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | Отзывы пользователей |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | Отзывы пользователей |
| `DeviceEvents` | `AntivirusDetection` | `EdrBlock` | Отзывы пользователей |





## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)