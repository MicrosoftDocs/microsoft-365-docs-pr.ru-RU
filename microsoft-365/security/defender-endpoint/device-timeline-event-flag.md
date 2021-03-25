---
title: Флаги событий событий Microsoft Defender для конечных устройств
description: Используйте флаги событий Времени событий Microsoft Defender для конечных устройств
keywords: Защитник для хронологии устройств конечной точки, флаги событий
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165157"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a>Флаги событий событий Microsoft Defender для конечных устройств

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Флаги событий в временной шкале устройств Defender для конечных точек помогают фильтровать и организовывать определенные события при расследовании возможных атак.

В временной шкале устройства Defender для конечных точек предоставляется хронологическое представление событий и связанных оповещений, наблюдаемых на устройстве. Этот список событий обеспечивает полную видимость любых событий, файлов и IP-адресов, наблюдаемых на устройстве. Иногда список может быть длительным. Флаги событий временной шкалы устройств помогают отслеживать события, которые могут быть связаны. 

После того как вы прошли временную шкалу устройства, вы можете сортировать, фильтровать и экспортировать определенные события, которые вы помечены.

Во время навигации по временной шкале устройства можно искать и фильтровать определенные события. Вы можете установить флаги событий по: 

- Выделение наиболее важных событий 
- Маркировка событий, которые требуют глубокого погружения 
- Создание хронологии чистого нарушения



## <a name="flag-an-event"></a>Пометить событие
1. Найдите событие, которое необходимо пометить
2. Щелкните значок флага в столбце Флаг. 
![Изображение флага временной шкалы устройства](images/device-flags.png)

## <a name="view-flagged-events"></a>Просмотр помеченных событий  
1. В разделе **Фильтры временной шкалы** в включить **помеченные события.**
2. Нажмите **Применить**. Отображаются только помеченные события.
Дополнительные фильтры можно применить, нажав на планку времени. В этом случае будут показываться события только до помеченного события.  
![Изображение флага временной шкалы устройства с фильтром](images/device-flag-filter.png)
