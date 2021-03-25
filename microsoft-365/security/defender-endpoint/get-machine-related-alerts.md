---
title: Получить API оповещений, связанных с машиной
description: Узнайте, как использовать API оповещений, связанных с машиной, для получения всех оповещений, связанных с определенным устройством в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, devices, related, alerts
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 837643bf5793437380a6f33c0eeca55ccef2100b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199255"
---
# <a name="get-machine-related-alerts--api"></a>Получить API оповещений, связанных с машиной

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Описание API
Извлекает все [оповещения, связанные](alerts.md) с определенным устройством.


## <a name="limitations"></a>Ограничения
1. Вы можете запрашивать на устройствах последнее обновление в соответствии с настроенным периодом хранения.
2. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.


Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Application |   Alert.Read.All |    'Read all alerts'
Application |   Alert.ReadWrite.All |   'Read and write all alerts'
Делегированное (рабочая или учебная учетная запись) | Alert.Read | 'Read alerts'
Делегированное (рабочая или учебная учетная запись) | Alert.ReadWrite | 'Read and write alerts'

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>- Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)
>- Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).

## <a name="http-request"></a>HTTP-запрос
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Авторизация | Строка | Bearer {token}. **Обязательное поле**.


## <a name="request-body"></a>Текст запроса
переменная Empty

## <a name="response"></a>Отклик
При успешном и устройстве существует — [](alerts.md) 200 ОК со списком сущностями оповещения в теле. Если устройство не найдено - 404 Не найдено.
