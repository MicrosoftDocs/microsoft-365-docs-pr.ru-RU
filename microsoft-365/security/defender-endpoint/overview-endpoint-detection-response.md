---
title: Обзор обнаружение и нейтрализация атак на конечные точки возможностей
ms.reviewer: ''
description: Узнайте о возможностях обнаружение и нейтрализация атак на конечные точки в Microsoft Defender для конечной точки
keywords: Защитник Microsoft для конечной точки, обнаружение и нейтрализация атак на конечные точки, ответ, обнаружение, кибербезопасность, защита
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
ms.openlocfilehash: b00bef611a3e4b33bf15a5366b09a96f68d4c1a2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933521"
---
# <a name="overview-of-endpoint-detection-and-response"></a>Обзор обнаружение и нейтрализация атак на конечные точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Средства Defender for Endpoint обнаружение и нейтрализация атак на конечные точки предоставляют расширенные средства обнаружения атак, которые находятся в режиме реального времени и могут быть готовы к действию. Аналитики систем безопасности могут эффективно определять приоритеты предупреждений, получать полную картину всех возможных брешей в системе безопасности, а также предпринимать действия по реагированию для устранения угроз.

При обнаружении угрозы в системе создаются предупреждения, которые затем исследуются аналитиками. Предупреждения, относящиеся к одинаковым методам атаки или к одному и тому же злоумышленнику, система агрегирует в объект, называемый _инцидентом_. Агрегирование предупреждений таким способом упрощает аналитикам выполнение обобщенных расследований угроз и реагирование на такие угрозы.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

Вдохновленный мышлением "предположить нарушение", Defender for Endpoint непрерывно собирает поведенческую кибер-телеметрию. Сюда входят сведения о процессах, действиях в сети, глубокий анализ ядра и диспетчера памяти, информация о действиях по входу в систему, об изменениях в реестре и файловой системе, а также о других действиях. Информация хранится в течение шести месяцев, благодаря чему аналитики могут изучать события вплоть до начала атаки. Затем аналитик может создать различные сводные представления и провести расследование в нескольких направлениях.

Функции реагирования позволяют быстро устранять угрозы, выполняя действия над затронутыми объектами.


## <a name="related-topics"></a>Статьи по теме
- [Панель мониторинга операций безопасности](security-operations-dashboard.md)
- [Очередь инцидентов](view-incidents-queue.md)
- [Очередь оповещений](alerts-queue.md)
- [Список устройств](machines-view-overview.md)

