---
title: Обзор пользовательских обнаружений в Microsoft 365 Defender
description: Понять, как можно использовать расширенный поиск для создания пользовательских обнаружений и создания оповещений
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, schema, kusto, microsoft 365, Microsoft Threat Protection
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae9617a55fd5efb40a3aba07202ebfb1494d4db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928812"
---
# <a name="custom-detections-overview"></a>Обзор настраиваемых обнаружений

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

С помощью настраиваемого обнаружения можно заблаговременно отслеживать различные события и состояния системы, включая подозрительные нарушения безопасности и неправильно настроенные конечные точки. Это можно сделать с помощью настраиваемых правил обнаружения, которые автоматически запускают оповещения, а также ответные действия.

Пользовательские обнаружения работают с [расширенным](advanced-hunting-overview.md)поиском, который предоставляет мощный гибкий язык запросов, который охватывает широкий набор событий и системных сведений из вашей сети. Вы можете настроить их на регулярный запуск с регулярными интервалами, создавая оповещения и принимая ответные действия при совпадениях.

Настраиваемые обнаружения обеспечивают:
- Оповещения об обнаружении на основе правил, основанные на расширенных запросах охоты
- Действия автоматического ответа

## <a name="related-topic"></a>Связанная тема
- [Создание пользовательских правил обнаружения и управление ими](custom-detection-rules.md)
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
