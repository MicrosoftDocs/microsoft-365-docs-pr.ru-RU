---
title: API инцидентов в Microsoft 365 Defender и тип ресурса инцидентов
description: Узнайте о методах и свойствах типа ресурса Incident в Microsoft 365 Defender
keywords: инцидент, инциденты, API
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928358"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>API инцидентов в Защитнике Microsoft 365 и тип ресурса инцидента

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Инцидент [—](incidents-overview.md) это коллекция связанных оповещений, которые помогают описать атаку. События из разных организаций в организации автоматически объединяются Защитником Microsoft 365. С помощью API инцидентов можно программным образом получать доступ к инцидентам и связанным оповещениям вашей организации.

## <a name="quotas-and-resource-allocation"></a>Квоты и выделение ресурсов

Можно запросить до 50 вызовов в минуту или 1500 вызовов в час. Каждый метод также имеет собственные квоты. Дополнительные сведения о квотах для конкретного метода см. в соответствующей статье о методе, который вы хотите использовать.

Код отклика HTTP указывает, что вы достигли квоты по количеству отправленных запросов или по выделению `429` времени работы. Тело ответа будет включать время, пока квота не будет сброшена.

## <a name="permissions"></a>Permissions

API инцидентов требует различных типов разрешений для каждого из своих методов. Дополнительные сведения о необходимых разрешениях см. в статье соответствующего метода.

## <a name="methods"></a>Методы

Метод | Возвращаемый тип | Описание
-|-|-
[Получение списка инцидентов](api-list-incidents.md) | [Список инцидентов](api-incident.md) | Получите список инцидентов.
[Обновление данных об инциденте](api-update-incidents.md) | [Инцидент](api-incident.md) | Обновление определенного инцидента.

## <a name="request-body-response-and-examples"></a>Тело запроса, ответ и примеры

Дополнительные сведения о том, как создать запрос или различенный ответ, а также практические примеры можно найти в соответствующих статьях о методе.

## <a name="common-properties"></a>Общие свойства

Свойство | Тип | Описание
-|-|-
incidentId | long | Уникальный ИД инцидента.
redirectIncidentId | nullable long | ИД инцидента, с который был объединен текущий инцидент.
incidentName | string | Имя инцидента.
createdTime | DateTimeOffset | Дата и время создания инцидента (в UTC).
lastUpdateTime | DateTimeOffset | Дата и время последнего обновления инцидента (в UTC).
assignedTo | string | Владелец инцидента.
severity | Перечисление | Серьезность инцидента. Возможные значения: ```UnSpecified``` , , , , и ```Informational``` ```Low``` ```Medium``` ```High``` .
status | Перечисление | Указывает текущее состояние инцидента. Возможные значения: ```Active``` , ```Resolved``` и ```Redirected``` .
classification | Перечисление | Спецификация инцидента. Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.
определение | Перечисление | Определяет определение инцидента. Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | string List | Список тегов инцидента.
alerts | Список оповещений | Список связанных оповещений. Примеры см. в документации по API [инцидентов](api-list-incidents.md) списка.

## <a name="related-articles"></a>Статьи по теме

- [Обзор API Microsoft 365 Defender](api-overview.md)
- [Обзор инцидентов](incidents-overview.md)
- [API списка инцидентов](api-list-incidents.md)
- [Обновление API инцидентов](api-update-incidents.md)
