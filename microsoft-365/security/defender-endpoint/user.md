---
title: Тип ресурса пользователя
description: Извлечение последних оповещений Microsoft Defender для конечных точек, связанных с пользователями.
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e3b2a567a953883d1d0ecd062159bfee4135dc85
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197961"
---
# <a name="user-resource-type"></a>Тип ресурса user

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Метод|Возвращаемый тип |Описание
:---|:---|:---
[Списки оповещений, связанных с пользователем](get-user-related-alerts.md) | Коллекция [alert](alerts.md) |  Список всех оповещений, связанных с [пользователем.](user.md)
[Список устройств, связанных с пользователем](get-user-related-machines.md) | [коллекция](machine.md) машин | Список всех устройств, которые были зарегистрированы [пользователем.](user.md)
