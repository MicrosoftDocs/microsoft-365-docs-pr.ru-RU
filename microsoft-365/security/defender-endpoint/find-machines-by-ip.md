---
title: Поиск устройств с помощью внутреннего API IP
description: Поиск устройств с запрашиваемой внутренней IP-адресой в диапазоне времени за 15 минут до и после заданного времени
keywords: apis, api graph, supported apis, get, device, IP, find, find device, by ip, ip
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 46afa945ce86c35e3af1c542eb1a9770041b3430
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769441"
---
# <a name="find-devices-by-internal-ip-api"></a>Поиск устройств с помощью внутреннего API IP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Описание API
Поиск [машин](machine.md) с запрашиваемой внутренней IP-адресой в диапазоне времени за 15 минут до и после заданного времени.


## <a name="limitations"></a>Ограничения
1. Данный период времени должен быть в течение последних 30 дней.
2. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.


## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Приложение |   Machine.Read.All |  'Read all machine profiles'
Приложение |   Machine.ReadWrite.All | 'Read and write all machine information'
Делегированные (рабочая или учебная учетная запись) | Machine.Read | 'Read machine information'
Делегированные (рабочая или учебная учетная запись) | Machine.ReadWrite | 'Read and write machine information'

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
> - В ответ будут включены только устройства, к которые пользователь имеет доступ на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).
> - Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)
> - В ответ будут включены только устройства, к которые пользователь имеет доступ на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).

## <a name="http-request"></a>HTTP-запрос
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Authorization | String | Bearer {token}. **Обязательное поле**.

## <a name="request-body"></a>Текст запроса
переменная Empty

## <a name="response"></a>Отклик
Если успешно — 200 ОК со списком машин в теле отклика.
Если время не в течение последних 30 дней - 400 bad request.

## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
