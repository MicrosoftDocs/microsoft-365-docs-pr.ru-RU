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
ms.openlocfilehash: de9fb28f09b88cf1730f3bb3539234f6a03ec2e3
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080717"
---
# <a name="custom-detections-overview"></a>Обзор настраиваемых обнаружений

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

С помощью пользовательских обнаружений можно заблаговременно отслеживать различные события и состояния системы, включая подозрительные нарушения безопасности и неправильно настроенные конечные точки, и реагировать на них. Это можно сделать с помощью настраиваемых правил обнаружения, которые автоматически запускают оповещения, а также ответные действия.

Настраиваемые обнаружения работают с [расширенным](advanced-hunting-overview.md)поиском, который предоставляет мощный гибкий язык запросов, который охватывает широкий набор событий и системных сведений из вашей сети. Вы можете настроить их на регулярный запуск, создавая оповещения и принимая ответные действия при совпадениях.

Настраиваемые обнаружения обеспечивают:
- Оповещения об обнаружении на основе правил, основанные на расширенных запросах охоты
- Действия автоматического ответа

## <a name="see-also"></a>См. также
- [Создание пользовательских правил обнаружения и управление ими](custom-detection-rules.md)
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Перенос запросов на расширенный поиск из Microsoft Defender для конечной точки](advanced-hunting-migrate-from-mdatp.md)
