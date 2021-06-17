---
title: Обновление API сущности машины
description: Узнайте, как обновить теги машин с помощью этого API. Вы можете обновить теги и свойства devicevalue.
keywords: apis, api graph, supported apis, get, alert, information, id
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985749"
---
# <a name="update-machine"></a>Машина обновления 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Описание API
Обновляет свойства существующей [машины.](machine.md)
<br>Updatable свойства: ```machineTags``` и ```deviceValue``` .


## <a name="limitations"></a>Ограничения
1. Можно обновить машины, доступные в API. 
2. Машина обновления только привносят теги в коллекцию тегов. Если теги существуют, они должны быть включены в коллекцию тегов в теле.
3. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.


## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Для приложения |   Machine.ReadWrite.All | 'Read and write machine information for all machines'
Делегированные (рабочая или учебная учетная запись) | Machine.ReadWrite | 'Read and write machine information'

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>- У пользователя должно быть по крайней мере следующее разрешение на роль: "Оповещение о расследовании". Дополнительные сведения см. в [дополнительных сведениях о создании и управлении ролями.](user-roles.md)
>- Пользователь должен иметь доступ к устройству, связанному с оповещением, в зависимости от параметров группы устройств. Дополнительные сведения см. в [дополнительных сведениях о создании и управлении группами устройств.](machine-groups.md)

## <a name="http-request"></a>HTTP-запрос
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Authorization | String | Bearer {token}. **Обязательное поле**.
Content-Type | String | application/json. **Обязательное поле**.


## <a name="request-body"></a>Текст запроса
В теле запроса укажи значения для соответствующих полей, которые должны быть обновлены.
<br>Предыдущие значения существующих свойств, не включенных в текст запроса, будут сохранены или вычислены повторно с учетом изменений, внесенных в значения других свойств. 
<br>Для лучшей производительности не следует включать существующие значения, которые не изменились.

Свойство | Тип | Описание
:---|:---|:---
machineTags | Коллекция объектов string | Набор [тегов](machine.md) машин.
deviceValue | Nullable Enum | Значение [устройства](tvm-assign-device-value.md). Возможные значения: "Нормальный", "Низкий" и "Высокий".

## <a name="response"></a>Отклик
В случае успешной работы этот метод возвращает [](machine.md) 200 ОК, а объект машины в теле ответа с обновленными свойствами. Если коллекция тегов машин в теле не содержит существующие теги машин - 400 Недействительный вход и сообщение, информирующие о отсутствующих тегах/s.
Если машина с указанным ИД не найдена - 404 Не найдено.


## <a name="example"></a>Пример

**Запрос**

Вот пример запроса.

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
