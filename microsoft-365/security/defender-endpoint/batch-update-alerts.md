---
title: API предупреждений о пакетном обновлении
description: Узнайте, как обновить оповещения Microsoft Defender для конечных точек в пакете с помощью этого API. Можно обновить свойства status, determination, classification и assignedTo.
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
ms.openlocfilehash: 80f88b31c1e07d1f40f3f58a1bd21b4a5c58c60b
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290211"
---
# <a name="batch-update-alerts"></a>Пакетные оповещения об обновлении

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Описание API

Обновляет свойства пакета существующих [оповещений.](alerts.md)

Отправка **комментариев** доступна с свойствами или без обновления.

Updatable свойства: `status` , `determination` и `classification` `assignedTo` .

## <a name="limitations"></a>Ограничения

1. Можно обновить оповещения, доступные в API. Дополнительные [сведения см. в](get-alerts.md) списке Оповещений.
2. Ограничения скорости для этого API : 10 вызовов в минуту и 500 вызовов в час.

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения | Разрешение | Имя отображения разрешений
:---|:---|:---
Application | Alerts.ReadWrite.All | 'Read and write all alerts'
Делегированные (рабочая или учебная учетная запись) | Alert.ReadWrite | 'Read and write alerts'

> [!NOTE]
> При получении маркера с помощью учетных данных пользователей:
>
> - У пользователя должно быть по крайней мере следующее разрешение на роль: "Оповещение о расследовании" (см. в рублях [Создание](user-roles.md) ролей и управление ими для получения дополнительных сведений)
> - Пользователь должен иметь доступ к устройству, связанному с оповещением, на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).

## <a name="http-request"></a>HTTP-запрос

```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Authorization | Строка | Bearer {token}. **Обязательное поле**.
Content-Type | String | application/json. **Обязательное поле**.

## <a name="request-body"></a>Текст запроса

В теле запроса поставляем ID-данные оповещений, которые необходимо обновить, и значения соответствующих полей, которые необходимо обновить для этих оповещений.

Предыдущие значения существующих свойств, не включенных в текст запроса, останутся прежними или будут повторно вычислены с учетом измененных значений других свойств.

Для достижения оптимальной производительности не следует включать существующие значения, которые не изменились.

Свойство | Тип | Описание
:---|:---|:---
alertIds | Строка &lt; списка&gt;| Список ID-списков оповещений, которые необходимо обновить. **Required**
status | String | Указывает обновленный статус указанных оповещений. Значения свойств: "New", "InProgress" и "Resolved".
assignedTo | String | Владелец указанных оповещений
classification | String | Указывает спецификацию указанных оповещений. Значения свойств: "Неизвестный", "FalsePositive", "TruePositive". 
определение | Строка | Указывает определение указанных оповещений. Значения свойств: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other"
comment | String | Комментарий, который необходимо добавить в указанные оповещения.

## <a name="response"></a>Отклик

В случае успешной работы этот метод возвращает 200 ОК с пустым телом отклика.

## <a name="example"></a>Пример

### <a name="request"></a>Запрос

Ниже приведен пример запроса.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
