---
title: Обновление API объекта оповещения
description: Узнайте, как обновить оповещение ATP защитника Майкрософт с помощью этого API. Можно обновить свойства status, determination, classification и assignedTo.
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
ms.technology: mde
ms.openlocfilehash: 7dd3ab3da34efa6cb954db2a596d7a1e48efedf1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199313"
---
# <a name="update-alert"></a>Обновление оповещения

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Описание API
Обновляет свойства существующего [оповещения.](alerts.md)
<br>Отправка **комментариев** доступна с свойствами или без обновления.
<br>Updatable свойства: ```status``` , ```determination``` и ```classification``` ```assignedTo``` .


## <a name="limitations"></a>Ограничения
1. Вы можете обновлять оповещения, доступные в API. Дополнительные [сведения см. в](get-alerts.md) списке Оповещений.
2. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.


## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Application |   Alerts.ReadWrite.All |  'Read and write all alerts'
Делегированное (рабочая или учебная учетная запись) | Alert.ReadWrite | 'Read and write alerts'

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>- У пользователя должно быть по крайней мере следующее разрешение на роль: "Оповещение о расследовании" (см. в рублях [Создание](user-roles.md) ролей и управление ими для получения дополнительных сведений)
>- Пользователь должен иметь доступ к устройству, связанному с оповещением, на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).

## <a name="http-request"></a>HTTP-запрос
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Авторизация | Строка | Bearer {token}. **Обязательное поле**.
Content-Type | String | application/json. **Обязательное поле**.


## <a name="request-body"></a>Текст запроса
В теле запроса укажи значения для соответствующих полей, которые должны быть обновлены.
<br>Предыдущие значения существующих свойств, не включенных в текст запроса, будут сохранены или вычислены повторно с учетом изменений, внесенных в значения других свойств. 
<br>Для лучшей производительности не следует включать существующие значения, которые не изменились.

Свойство | Тип | Описание
:---|:---|:---
status | String | Указывает текущее состояние оповещений. Значения свойств: "New", "InProgress" и "Resolved".
assignedTo | String | Владелец оповещений
classification | String | Указывает спецификацию оповещений. Значения свойств: "Неизвестный", "FalsePositive", "TruePositive". 
определение | Строка | Указывает определение оповещений. Значения свойств: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other"
comment | String | Комментарий, который необходимо добавить в оповещение.

## <a name="response"></a>Отклик
В случае успешной работы этот метод возвращает [](alerts.md) 200 ОК, а объект оповещения в теле ответа с обновленными свойствами. Если оповещение с указанным id не найдено - 404 Не найдено.


## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
