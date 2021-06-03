---
title: Microsoft 365 Defender incidents API and the incidents resource type
description: Узнайте о методах и свойствах типа ресурсов Incidents в Microsoft 365 Defender
keywords: инциденты, инциденты, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 587d6107b0c09b2178311d8da6606968e7fda083
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730934"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a>Microsoft 365 API инцидентов Defender и тип ресурса инцидентов

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

Инцидент [—](incidents-overview.md) это набор связанных оповещений, которые помогают описать атаку. События из разных сущностями в вашей организации автоматически агрегируются Microsoft 365 Defender. API инцидентов можно использовать для программного доступа к инцидентам и связанным оповещениям организации.

## <a name="quotas-and-resource-allocation"></a>Квоты и распределение ресурсов

Вы можете запрашивать до 50 вызовов в минуту или 1500 вызовов в час. Каждый метод также имеет свои квоты. Дополнительные сведения о квотах, определенных методом, см. в соответствующей статье для метода, который вы хотите использовать.

Код ответа HTTP указывает, что вы достигли квоты либо по количеству отправленных запросов, либо по `429` выделенной продолжительной работе. В органе ответа будет включено время, пока квота, которая была достигнута, не будет сброшена.

## <a name="permissions"></a>Разрешения

API инцидентов требует различных разрешений для каждого из его методов. Дополнительные сведения о необходимых разрешениях см. в статье соответствующего метода.

## <a name="methods"></a>Методы

Метод | Возвращаемый тип | Описание
-|-|-
[Получение списка инцидентов](api-list-incidents.md) | [Список инцидентов](api-incident.md) | Получите список инцидентов.
[Обновление данных об инциденте](api-update-incidents.md) | [Инцидент](api-incident.md) | Обновление определенного инцидента.

## <a name="request-body-response-and-examples"></a>Запрос тела, ответа и примеров

Дополнительные сведения о том, как создать запрос или размыть ответ, а также практические примеры.

## <a name="common-properties"></a>Общие свойства

Свойство | Тип | Описание
-|-|-
incidentId | long | Уникальный ID инцидента.
redirectIncidentId | nullable long | ID инцидента, в который был объединено текущее происшествие.
incidentName | Строка | Имя инцидента.
createdTime | DateTimeOffset | Дата и время (в UTC) был создан инцидент.
lastUpdateTime | DateTimeOffset | Дата и время (в UTC) инцидент был последним обновлением.
assignedTo | Строка | Владелец инцидента.
severity | Перечисление | Серьезность инцидента. Возможные значения: ```UnSpecified``` ```Informational``` , , , , ```Low``` и ```Medium``` ```High``` .
status | Перечисление | Указывает текущее состояние инцидента. Возможные значения: ```Active``` , ```Resolved``` и ```Redirected``` .
classification | Перечисление | Спецификация инцидента. Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.
определение | Перечисление | Указывает определение инцидента. Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | строка Список | Список тегов Инцидент.
comments | Список комментариев об инцидентах | Объект Комментарий инцидента содержит строку комментариев, созданную строкуBy и время даты созданияTime.
alerts | Список оповещений | Список связанных оповещений. Примеры см. в [документации API инцидентов](api-list-incidents.md) списка.

## <a name="related-articles"></a>Связанные статьи

- [Microsoft 365 Обзор API defender](api-overview.md)
- [Обзор инцидентов](incidents-overview.md)
- [API инцидентов списка](api-list-incidents.md)
- [Обновление API инцидента](api-update-incidents.md)
