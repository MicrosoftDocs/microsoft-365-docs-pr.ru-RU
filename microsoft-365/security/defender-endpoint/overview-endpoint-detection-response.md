---
title: Обзор возможностей обнаружения конечных точек и ответов
ms.reviewer: ''
description: Узнайте о возможностях обнаружения конечных точек и ответов в Microsoft Defender для конечной точки
keywords: защитник Microsoft для конечной точки, обнаружения конечных точек и ответа, ответа, обнаружения, кибербезопасности, защиты
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 138a6afde9e8c601fd41811928580644b85bf2e2
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861723"
---
# <a name="overview-of-endpoint-detection-and-response"></a>Обзор обнаружения конечных точек и ответа

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Функции обнаружения конечных точек и ответов Defender для конечной точки предоставляют расширенные обнаружения атак, которые находятся в режиме реального времени и могут быть готовы к действию. Аналитики систем безопасности могут эффективно определять приоритеты предупреждений, получать полную картину всех возможных брешей в системе безопасности, а также предпринимать действия по реагированию для устранения угроз.

При обнаружении угрозы в системе создаются предупреждения, которые затем исследуются аналитиками. Предупреждения, относящиеся к одинаковым методам атаки или к одному и тому же злоумышленнику, система агрегирует в объект, называемый _инцидентом_. Агрегирование предупреждений таким способом упрощает аналитикам выполнение обобщенных расследований угроз и реагирование на такие угрозы.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

Вдохновленный мышлением "предположить нарушение", Defender for Endpoint непрерывно собирает поведенческую кибер-телеметрию. Сюда входят сведения о процессах, действиях в сети, глубокий анализ ядра и диспетчера памяти, информация о действиях по входу в систему, об изменениях в реестре и файловой системе, а также о других действиях. Информация хранится в течение шести месяцев, благодаря чему аналитики могут изучать события вплоть до начала атаки. Затем аналитик может создать различные сводные представления и провести расследование в нескольких направлениях.

Функции реагирования позволяют быстро устранять угрозы, выполняя действия над затронутыми объектами.


## <a name="related-topics"></a>Похожие темы
- [Панель мониторинга операций безопасности](security-operations-dashboard.md)
- [Очередь инцидентов](view-incidents-queue.md)
- [Очередь оповещений](alerts-queue.md)
- [Список устройств](machines-view-overview.md)

