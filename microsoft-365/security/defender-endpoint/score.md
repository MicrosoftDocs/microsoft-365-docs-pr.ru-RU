---
title: Методы и свойства оценки
description: Извлекает оценку экспозиции организации, оценку безопасности устройства и оценку экспозиции по группе устройств
keywords: apis, graph api, supported apis, score, exposure score, device secure score, exposure score by device group
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89012dce4aa5b74d09f071b23f7709b4bd0bf03c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771434"
---
# <a name="score-resource-type"></a>Тип ресурса Score

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Методы

Метод |Возвращаемый тип |Описание
:---|:---|:---
[Получить показатель уязвимости](get-exposure-score.md) | [Показатель](score.md) | Получите оценку экспозиции организации.
[Получить оценку безопасности устройства](get-device-secure-score.md) | [Показатель](score.md) | Получите безопасную оценку для устройства организации.
[Оценка экспозиции списка по группе устройств](get-machine-group-exposure-score.md)| [Показатель](score.md) | Список баллов по группе устройств.

## <a name="properties"></a>Свойства

Свойство |  Тип    |   Описание
:---|:---|:---
Оценка | Двойное с плавающей точкой | Текущий балл.
Time | DateTime | Дата и время, в течение которых был сделан вызов для этого API.
RbacGroupName | String | Имя группы устройств.
