---
title: Microsoft 365 Инциденты с API-ресурсами защитника и тип ресурсов инцидента
description: Узнайте о методах и свойствах типа ресурса «Инцидент» в Microsoft 365 Defender
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
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572589"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 Api инцидентов защитника и тип ресурса инцидента

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

Инцидент [представляет собой](incidents-overview.md) набор связанных оповещений, которые помогают описать атаку. События из разных сущностей в вашей организации автоматически агрегируются Microsoft 365 Defender. API инцидентов можно использовать для программного доступа к инцидентам и связанным с ними оповещениям организации.

## <a name="quotas-and-resource-allocation"></a>Квоты и распределение ресурсов

Вы можете запросить до 50 звонков в минуту или 1500 звонков в час. Каждый метод также имеет свои собственные квоты. Для получения дополнительной информации о конкретных методах квот, см.

Код `429` ответа HTTP указывает на то, что вы достигли квоты либо по количеству отправленных запросов, либо по отведенному времени работы. Орган реагирования будет включать время, пока квота, которую вы достигли, будет сброшена.

## <a name="permissions"></a>Разрешения

API инцидентов требует различных видов разрешений для каждого из своих методов. Для получения дополнительной информации о необходимых разрешениях см.

## <a name="methods"></a>Методы

Метод | Возвращаемый тип | Описание
-|-|-
[Получение списка инцидентов](api-list-incidents.md) | [Список инцидентов](api-incident.md) | Получить список инцидентов.
[Обновление данных об инциденте](api-update-incidents.md) | [Инцидент](api-incident.md) | Обновление конкретного инцидента.

## <a name="request-body-response-and-examples"></a>Орган запроса, ответ и примеры

Для получения более подробной информации о том, как построить запрос или разобрать ответ, и для практических примеров обратитесь к соответствующим статьям метода.

## <a name="common-properties"></a>Общие свойства

Свойство | Тип | Описание
-|-|-
инцидентИд | long | Инцидент уникальный идентификатор.
перенаправитьИдентид | нулевой долго | Идентификатор инцидента, к который был объединен текущий инцидент.
инцидентИмя | Строка | Название Инцидента.
созданTime | DateTimeOffset | Дата и время (в UTC) Инцидент был создан.
lastUpdateTime | DateTimeOffset | Дата и время (в UTC) Инцидент был в последний раз обновлен.
assignedTo | Строка | Владелец инцидента.
severity | Перечисление | Тяжесть инцидента. Возможные значения: ```UnSpecified``` ```Informational``` , , , и ```Low``` ```Medium``` ```High``` .
status | Перечисление | Уточняется текущее состояние происшествия. Возможные значения: ```Active``` ```Resolved``` , и ```Redirected``` .
classification | Перечисление | Спецификация инцидента. Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.
решимость | Перечисление | Уточняется определение инцидента. Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | строка Список | Список тегов инцидента.
comments | Список комментариев по инцидентам | Объект Комментарий инцидента содержит: строку комментариев, созданную строкой и создать Время даты.
alerts | Список оповещений | Список связанных оповещений. Смотрите примеры в [документации API по инцидентам](api-list-incidents.md) списка.

## <a name="related-articles"></a>Связанные статьи

- [Microsoft 365 Обзор API-и защитников](api-overview.md)
- [Обзор инцидентов](incidents-overview.md)
- [Список инцидентов API](api-list-incidents.md)
- [Обновление API инцидента](api-update-incidents.md)
