---
title: Методы и свойства программного обеспечения
description: Извлекает последние оповещений.
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9bfec2c4e65a390189556c14347eaf17236fb95e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187304"
---
# <a name="software-resource-type"></a>Тип ресурсов программного обеспечения

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Методы

Метод |Возвращаемый тип |Описание
:---|:---|:---
[Список программного обеспечения](get-software.md) | Коллекция программного обеспечения | Список инвентаризации программного обеспечения организации.
[Получить программное обеспечение по ID](get-software-by-id.md) | Программное обеспечение | Получите определенное программное обеспечение по его программному ИД.
[Список распространения версий программного обеспечения](get-software-ver-distribution.md)| Коллекция рассылки | Список распространения программных версий по ID программного обеспечения.
[Список машин по программному обеспечению](get-machines-by-software.md)| Коллекция MachineRef | Извлечение списка устройств, связанных с программным ИД.
[Список уязвимостей по программному обеспечению](get-vuln-by-software.md) | [Коллекция уязвимостей](vulnerability.md) | Извлечение списка уязвимостей, связанных с программным ИД.
[Отсутствие КБ](get-missing-kbs-software.md) | Коллекция KB | Получить список отсутствующих KBs, связанных с ID программного обеспечения

## <a name="properties"></a>Свойства

Свойство |   Тип   |   Описание
:---|:---|:---
id | Строка | ID программного обеспечения
Имя | Строка | Имя программного обеспечения
Поставщик | Строка | Имя поставщика программного обеспечения
Недостатки | Длинное целое | Количество обнаруженных уязвимостей
publicExploit | Boolean | Существует публичный эксплойт для некоторых уязвимостей
activeAlert | Boolean | Активное оповещение связано с этим программным обеспечением
exposedMachines | Длинное целое | Количество открытых устройств
impactScore | Двойное с плавающей точкой | Влияние оценки экспозиции этого программного обеспечения
