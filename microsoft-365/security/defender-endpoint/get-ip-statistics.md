---
title: Получить API статистики IP
description: Получите последнюю статистику для IP-адреса с помощью Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, get, ip, statistics, prevalence
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
ms.openlocfilehash: 4919f082c115d8a57960ec49532b6cda6a63833f
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998732"
---
# <a name="get-ip-statistics-api"></a>Получить API статистики IP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Описание API
Извлекает статистику для данного IP- адреса.

## <a name="limitations"></a>Ограничения
1. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.

## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Приложение |   Ip.Read.All |   'Read IP address profiles'
Делегированные (рабочая или учебная учетная запись) | Ip.Read.All |  'Read IP address profiles'

>[!NOTE]
> При получении маркера с помощью учетных данных пользователей:
>- Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)

## <a name="http-request"></a>HTTP-запрос

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Авторизация | String | Bearer {token}. **Обязательное поле**.

## <a name="request-uri-parameters"></a>Запрос параметров URI

Имя | Тип | Описание
:---|:---|:---
lookBackHours | Int32 | Определяет часы поиска, чтобы получить статистику. По умолчанию до 30 дней. **Необязательное поле**.

## <a name="request-body"></a>Текст запроса
переменная Empty

## <a name="response"></a>Отклик
При успешном и ip существует - 200 ОК со статистическими данными в теле. IP не существует - 404 Не найдено.


## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

**Отклик**

Ниже приведен пример отклика.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| Имя | Описание |
| :--- | :---------- |
| Распространенность организации | отчетливое количество устройств, открывав сетевое подключение к этому IP. |
| Первое увидено в Org | первое подключение для этого IP-адреса в организации. |
| Org последний раз видели  | последнее подключение для этого IP-адреса в организации. |

> [!NOTE]
> Эта статистика основана на данных за последние 30 дней. 
