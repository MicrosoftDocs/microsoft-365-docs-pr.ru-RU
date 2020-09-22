---
title: Тип ресурса "инцидент" в API Microsoft Threat protection
description: Сведения о методах и свойствах типа ресурса инцидента в защите от угроз Майкрософт
keywords: инцидент, происшествия, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: ac149ca7263b8ef8bb37a7dd18bf0787a3114b37
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201307"
---
# <a name="incident-resource-type"></a>Тип ресурса инцидента

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)

>[!IMPORTANT] 
>Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="methods"></a>Методы

Метод |Возвращаемый тип |Описание
:---|:---|:---
[Получение списка инцидентов](api-list-incidents.md) | Список [инцидентов](api-incident.md) | Получение списка инцидентов.
[Обновление данных об инциденте](api-update-incidents.md) | [Случаях](api-incident.md) | Обновление конкретного инцидента.


## <a name="properties"></a>Свойства

Свойство |    Тип    |    Описание
:---|:---|:---
инЦидентид | long | Уникальный идентификатор инцидента.
редиректинЦидентид | Long, допускающий значение null | Идентификатор инцидента, с которым было выполнено слияние текущего инцидента.
инЦидентнаме | string | Имя инцидента.
createdTime | DateTimeOffset | Дата и время создания инцидента (в формате UTC).
lastUpdateTime | DateTimeOffset | Дата и время последнего обновления инцидента (в формате UTC).
assignedTo | string | Владелец инцидента.
severity | Перечисление | Степень серьезности инцидента. Возможные значения: ```UnSpecified``` , ```Informational``` , ```Low``` ```Medium``` и ```High``` .
status | Перечисление | Указывает текущее состояние инцидента. Возможные значения: ```Active``` ```Resolved``` и ```Redirected``` .
classification | Перечисление | Спецификация инцидента. Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.
решение | Перечисление | Указывает на определение инцидента. Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Список строк | Список тегов инцидента.
alerts | Список оповещений | Список связанных оповещений. В этой статье приведены примеры документации по API [происшествий](api-list-incidents.md) .
