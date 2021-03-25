---
title: Тип ресурса исследования
description: Объект исследования ATP Защитника Майкрософт.
keywords: apis, graph api, supported apis, get, alerts, investigations
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 36adf0fa5c0de79fe0616f1216118a98ba2005a4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187352"
---
# <a name="investigation-resource-type"></a>Тип ресурса исследования

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Представляете объект автоматического расследования в Защитнике для конечной точки.
<br> Дополнительные [сведения см.](automated-investigations.md) в обзоре автоматизированных расследований.

## <a name="methods"></a>Методы
Метод|Возвращаемый тип |Описание
:---|:---|:---
[Исследования списка](get-investigation-collection.md) | Коллекция исследований | Get collection of Investigation
[Получить одно исследование](get-investigation-object.md) | Объект исследования | Получает одно целое исследование.
[Начало расследования](initiate-autoir-investigation.md) | Объект исследования | Запускает исследование на устройстве.


## <a name="properties"></a>Свойства
Свойство |  Тип    |   Описание
:---|:---|:---
id | Строка | Удостоверение объекта расследования. 
startTime | DateTime Nullable | Дата и время создания расследования. 
endTime | DateTime Nullable | Дата и время завершения расследования. 
cancelledBy | Строка | ID пользователя или приложения, отменив это расследование. 
investigationState | Перечисление | Текущее состояние расследования. Возможные значения: "Unknown", "Terminated", "SuccessfullyRemediated", 'Benign', 'Failed', 'PartiallyRemediated', "Running", "PendingApproval", "PendingResource", "PartiallyInvestigated", "TerminatedByUser", "TerminatedBySystem", "Queued", "InnerFailure", "PreexistingAlert", "UnsupportedAlert", "SuppressedAlert".
statusDetails | Строка | Дополнительные сведения о состоянии расследования.
machineId | Строка | ID устройства, на котором выполняется расследование.
computerDnsName | Строка | Имя устройства, на котором выполняется расследование.
triggeringAlertId | Строка | ID оповещений, которые вызвали расследование.


## <a name="json-representation"></a>Представление Json

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
