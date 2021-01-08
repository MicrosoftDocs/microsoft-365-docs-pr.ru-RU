---
title: Изменение имен в схеме advanced hunting в Microsoft 365 Defender
description: Отслеживание и проверка изменений именования таблиц и столбцов в схеме расширенных поисков
keywords: расширенный поиск, охота на угрозы, поиск киберугроз, защита от угроз (Майкрософт), Microsoft 365, mtp, m365, поиск, запрос, телеметрия, справочник по схеме, kusto, таблица, данные, изменения именования, переименование, Защита от угроз (Майкрософт)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 0bef5f4abcaf0d57af9c160ff31f859c2536ccd2
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780815"
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
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailAction | EmailAction | Отзывы пользователей |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicy | EmailActionPolicy | Отзывы пользователей |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicyGuid | EmailActionPolicyGuid | Отзывы пользователей |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)