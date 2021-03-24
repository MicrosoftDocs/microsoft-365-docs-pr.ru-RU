---
title: Обзор пользовательских обнаружений в ATP Защитника Майкрософт
ms.reviewer: ''
description: Понять, как можно использовать расширенный поиск для создания настраиваемой диагностики и создания оповещений
keywords: настраиваемые обнаружения, оповещения, правила обнаружения, расширенные охоты, охота, запрос, действия отклика, интервал, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6c9befcc4b1224cacb2ab4eb8530e30a397aab49
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069051"
---
# <a name="custom-detections-overview"></a>Обзор настраиваемых обнаружений

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


С помощью настраиваемого обнаружения можно активно отслеживать различные события и состояния системы и реагировать на них, в том числе заподозрить нарушения и неправильно настроенные устройства. Это можно сделать с помощью настраиваемых правил обнаружения, автоматически запускаемых оповещений и ответных действий.

Настраиваемые обнаружения [](advanced-hunting-overview.md)работают с расширенными средствами охоты, которые предоставляют мощный гибкий язык запросов, который охватывает широкий набор событий и системных сведений из сети. Вы можете настроить их для запуска с регулярными интервалами, создавая оповещения и принимая ответные действия при совпадениях.

Настраиваемые обнаружения обеспечивают:
- Оповещений об обнаружении на основе правил, построенных из расширенных запросов на охоту
- Действия автоматического ответа, применимые к файлам и устройствам

## <a name="related-topics"></a>Статьи по теме
- [Создание правил обнаружения](custom-detection-rules.md)
- [Просмотр и управление правилами обнаружения](custom-detections-manage.md)
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
