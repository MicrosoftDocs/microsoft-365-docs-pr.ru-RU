---
title: API машин списка
description: Узнайте, как использовать API машин Списка для получения коллекции машин, которые взаимодействовали с облаком ATP Microsoft Defender.
keywords: apis, graph api, supported apis, get, devices
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
ms.openlocfilehash: 23997cf4997ccfea8ee89a9b9ec5cc991dfa1ed0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200381"
---
# <a name="list-machines-api"></a>API машин списка

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Описание API
Извлекает коллекцию [машин,](machine.md) которые связывались с облаком Microsoft Defender для конечной точки.
<br>Поддерживает [запросы OData V4.](https://www.odata.org/documentation/)
<br>Запрос OData поддерживается `$filter` на: `computerDnsName` , , , , и `lastSeen` `healthStatus` `osPlatform` `riskScore` `rbacGroupId` .
<br>Примеры запросов [OData](exposed-apis-odata-samples.md) с Defender для endpoint


## <a name="limitations"></a>Ограничения
1. Устройства можно получить в последний раз в соответствии с настроенным периодом хранения.
2. Максимальный размер страницы — 10 000.
3. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час. 


## <a name="permissions"></a>Разрешения

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Application |   Machine.Read.All |  'Read all machine profiles'
Application |   Machine.ReadWrite.All | 'Read and write all machine information'
Делегированное (рабочая или учебная учетная запись) | Machine.Read | 'Read machine information'
Делегированное (рабочая или учебная учетная запись) | Machine.ReadWrite | 'Read and write machine information'

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>- Пользователю необходимо иметь по крайней мере следующее разрешение на роль: "Просмотр данных" (см. [создание](user-roles.md) и управление ролями для получения дополнительных сведений)
>- Ответ будет включать только устройства, к которые пользователь имеет доступ на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).

## <a name="http-request"></a>HTTP-запрос

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Авторизация | Строка | Bearer {token}. **Обязательное поле**.


## <a name="request-body"></a>Текст запроса
переменная Empty

## <a name="response"></a>Отклик
Если успешно и машины существуют — 200 ОК со списком машинных [](machine.md) сущностями в теле. Если нет недавних машин - 404 Не найдено.


## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

**Отклик**

Ниже приведен пример отклика.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Статьи по теме
- [Запросы OData в Microsoft Defender для конечной точки](exposed-apis-odata-samples.md)
