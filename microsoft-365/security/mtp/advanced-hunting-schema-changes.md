---
title: Изменение имен в схеме advanced hunting в Microsoft 365 Defender
description: Отслеживание и проверка именования таблиц и столбцов в схеме расширенных поисков
keywords: расширенный поиск, охота на угрозы, поиск киберугроз, защита от угроз (Майкрософт), Microsoft 365, mtp, m365, поиск, запрос, телеметрия, справочник по схеме, kusto, таблица, данные, изменения именования, переименование, Защита от угроз (Майкрософт)
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
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066873"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Схема "Расширенный поиск" — изменения именования

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Схема [расширенных поисков регулярно](advanced-hunting-schema-tables.md) обновляется для добавления новых таблиц и столбцов. В некоторых случаях существующие имена столбцов переименовываются или заменяются для улучшения пользовательского интерфейса. В этой статье вы можете просмотреть изменения именования, которые могут повлиять на ваши запросы.

Изменения именования автоматически применяются к запросам, сохраненным в центре безопасности, включая запросы, используемые пользовательскими правилами обнаружения. Вам не нужно обновлять эти запросы вручную. Однако вам потребуется обновить следующие запросы:
- Запросы, которые запускаются с помощью API
- Запросы, сохраненные в другом месте за пределами центра безопасности

## <a name="december-2020"></a>Декабрь 2020 г.

| Имя таблицы | Исходное имя столбца | Имя нового столбца | Причина изменения
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | Отзывы пользователей |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | Отзывы пользователей |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | Отзывы пользователей |

## <a name="january-2021"></a>Январь 2021 г.

| Имя столбца | Имя исходного значения | Новое имя значения | Причина изменения
|--|--|--|--|
| `DetectionSource` | MCAS |    Microsoft Cloud App Security | Rebranding |
| `DetectionSource` | WindowsDefenderAtp|   EDR| Rebranding |
| `DetectionSource` | WindowsDefenderAv | Защита от вирусов | Rebranding |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | Rebranding |
| `DetectionSource` | CustomerTI |  Настраиваемая ti | Rebranding |
| `DetectionSource` | OfficeATP | Microsoft Defender для Office 365 | Rebranding |
| `DetectionSource` | MTP   | Microsoft 365 Defender | Rebranding |
| `DetectionSource` | AzureATP |    Microsoft Defender для удостоверений | Rebranding |
| `DetectionSource` | CustomDetection   | Пользовательское обнаружение | Rebranding |
| `DetectionSource` | AutomatedInvestigation |Автоматическое исследование | Rebranding |
| `DetectionSource` | ThreatExperts | Эксперты Майкрософт по угрозам | Rebranding |
| `DetectionSource` | Сторонний ti | Сторонние датчики | Rebranding |
| `ServiceSource` | ATP в Microsoft Defender — это| Microsoft Defender для конечной точки | Rebranding |
|`ServiceSource` |Защита от угроз (Майкрософт)   | Microsoft 365 Defender | Rebranding |
| `ServiceSource` | Office 365 ATP  |Microsoft Defender для Office 365 | Rebranding |
| `ServiceSource` |Azure ATP    |Microsoft Defender для удостоверений | Rebranding |

`DetectionSource`доступен в таблице [AlertInfo.](advanced-hunting-alertinfo-table.md) `ServiceSource`доступен в [таблицах AlertEvidence](advanced-hunting-alertevidence-table.md) и [AlertInfo.](advanced-hunting-alertinfo-table.md) 
## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)