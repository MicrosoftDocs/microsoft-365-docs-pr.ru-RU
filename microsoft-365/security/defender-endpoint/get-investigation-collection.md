---
title: API списков расследований
description: Используйте этот API для создания вызовов, связанных с сбором расследований
keywords: apis, graph api, supported apis, Investigations collection
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
ms.openlocfilehash: 38485a5028626153c26cd1e11537ef7a2daf5296
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770149"
---
# <a name="list-investigations-api"></a>API списков расследований

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Описание API
Извлекает коллекцию [исследований.](investigation.md)
<br>Поддерживает [запросы OData V4.](https://www.odata.org/documentation/)
<br>Запрос OData поддерживается ```$filter``` на: ```startTime``` и ```state``` ```machineId``` ```triggeringAlertId``` свойствах.
<br>Примеры запросов [OData в Microsoft Defender для конечной точки](exposed-apis-odata-samples.md)


## <a name="limitations"></a>Ограничения
1. Максимальный размер страницы — 10 000.
2. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час. 


## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Приложение |   Alert.Read.All |    'Read all alerts'
Приложение |   Alert.ReadWrite.All |   'Read and write all alerts'
Делегированные (рабочая или учебная учетная запись) | Alert.Read | 'Read alerts'
Делегированные (рабочая или учебная учетная запись) | Alert.ReadWrite | 'Read and write alerts'

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>- Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)

## <a name="http-request"></a>HTTP-запрос
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Authorization | String | Bearer {token}. **Обязательное поле**.


## <a name="request-body"></a>Текст запроса
переменная Empty

## <a name="response"></a>Отклик
В случае успешной работы этот метод возвращает 200 код ответа Ok с набором [сущностями Investigations.](investigation.md)


## <a name="example"></a>Пример

**Запрос**

Вот пример запроса на все исследования: 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

**Отклик**

Вот пример ответа:

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
