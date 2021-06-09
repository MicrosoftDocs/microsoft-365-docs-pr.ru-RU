---
title: Получите API пользователей с логотипами машин
description: Узнайте, как использовать API пользователей с логотипом get machine для получения коллекции зарегистрированных пользователей на устройстве в Microsoft Defender for Endpoint.
keywords: apis, api graph, supported apis, get, device, log on, users
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 1c81d2978677b751a8085f88b5c4732fd4a5a247
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770053"
---
# <a name="get-machine-logon-users-api"></a>Получите API пользователей с логотипами машин

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Описание API
Извлекает коллекцию в журнале пользователей на определенном устройстве.


## <a name="limitations"></a>Ограничения
1. Вы можете запрашивать последние обновления оповещений в соответствии с настроенным периодом хранения.
2. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.


## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Для приложений |   User.Read.All | 'Read user profiles'
Делегированные (рабочая или учебная учетная запись) | User.Read.All | 'Read user profiles'

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>- У пользователя должно быть по крайней мере следующее разрешение на роль: "Просмотр данных". Дополнительные сведения см. в [дополнительных сведениях о создании и управлении ролями](user-roles.md) )
>- Ответ будет включать пользователей только в том случае, если устройство отображается пользователю в зависимости от параметров группы устройств. Дополнительные сведения см. в [дополнительных сведениях о создании и управлении группами устройств.](machine-groups.md)

## <a name="http-request"></a>HTTP-запрос
```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Авторизация | String | Bearer {token}. **Обязательное поле**.


## <a name="request-body"></a>Тело запроса
переменная Empty

## <a name="response"></a>Отклик
При успешном и устройстве существует 200 ОК со списком пользовательских [](user.md) сущностями в теле. Если устройство не найдено - 404 Не найдено.


## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

**Отклик**

Ниже приведен пример отклика.


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
