---
title: Получите API коллекции групп машин RBAC
description: Узнайте, как использовать API коллекции Get KB для получения коллекции групп устройств RBAC в Microsoft Defender for Endpoint.
keywords: apis, graph api, supported apis, get, RBAC, group
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/07/2018
ms.openlocfilehash: 18566025d79f02281c1d2c1509dd98f1e57879c2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932779"
---
# <a name="get-kb-collection-api"></a>Получить API коллекции KB

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Извлекает коллекцию групп устройств RBAC.

## <a name="permissions"></a>Разрешения
Пользователю нужны разрешения на чтение.

## <a name="http-request"></a>HTTP-запрос
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a>Заголовки запросов

Заголовок | Значение 
:---|:---
Авторизация | Bearer {token}. **Обязательное поле**.
Тип контента | application/json

## <a name="request-body"></a>Текст запроса
переменная Empty

## <a name="response"></a>Отклик
Если успешно - 200 ОК.

## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

**Отклик**

Ниже приведен пример отклика.
Полевой id содержит **id** группы устройств и равен **полевой rbacGroupId** в сведениях о устройствах. **Негруппировка** поля относится только к одной группе для всех устройств, которые не были назначены какой-либо группе. Эта группа, как обычно, имеет имя UnassignedGroup.

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
