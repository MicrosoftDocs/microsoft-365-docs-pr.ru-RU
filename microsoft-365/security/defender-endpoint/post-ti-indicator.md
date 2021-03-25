---
title: Отправка или обновление API индикатора
description: Узнайте, как использовать API отправки или обновления индикатора для отправки или обновления нового объекта индикатора в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, submit, ti, indicator, update
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
ms.openlocfilehash: 42bab0a9d20d5e1ef78b98b3538cef209240d890
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187360"
---
# <a name="submit-or-update-indicator-api"></a>Отправка или обновление API индикатора

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Описание API
Отправка или обновление новой сущности [индикатора.](ti-indicator.md)
<br>Нотация CIDR для ИП не поддерживается.

## <a name="limitations"></a>Ограничения
1. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.
2. Существует ограничение в 15 000 активных индикаторов на одного клиента. 


## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные новости, в том числе выбор разрешений, см. в [руб. Начало работы](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Приложение |   Ti.ReadWrite |  'Read and write Indicators'
Приложение |   Ti.ReadWrite.All |  'Read and write All Indicators'
Делегированное (рабочая или учебная учетная запись) |    Ti.ReadWrite |  'Read and write Indicators'


## <a name="http-request"></a>HTTP-запрос
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Авторизация | Строка | Bearer {token}. **Обязательное поле**.
Content-Type | string | application/json. **Обязательное поле**.

## <a name="request-body"></a>Текст запроса
В теле запроса поставляем объект JSON со следующими параметрами:

Параметр | Тип    | Описание
:---|:---|:---
indicatorValue | Строка | Удостоверение сущности [индикатора.](ti-indicator.md) **Required**
indicatorType | Перечисление | Тип индикатора. Возможные значения: "FileSha1", "FileSha256", "IpAddress", "DomainName" и "URL". **Required**
action | Перечисление | Действие, которое будет принято, если индикатор будет обнаружен в организации. Возможные значения: "Alert", "AlertAndBlock" и "Allowed". **Required**
приложение | Строка | Приложение, связанное с индикатором. **Необязательное**
title | Строка | Название оповещений индикатора. **Required**
description | Строка | Описание индикатора. **Required**
expirationTime | DateTimeOffset | Срок действия индикатора. **Необязательное**
severity | Перечисление | Серьезность индикатора. Возможные значения: "Информационная", "Низкая", "Средняя" и "Высокая". **Необязательное**
recommendedActions | Строка | Предупреждение индикатора TI рекомендуемые действия. **Необязательное**
rbacGroupNames | Строка | Разделенный запятой список имен групп RBAC, к который будет применен индикатор. **Необязательное**


## <a name="response"></a>Отклик
- В случае успешной работы этот метод возвращает 200 — код ответа OK и созданную /обновленную сущность [Индикатора](ti-indicator.md) в тексте ответа.
- Если не удалось: этот метод возвращает 400 — Bad Request. Плохой запрос обычно указывает неправильное тело.

## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a>Связанная тема
- [Управление индикаторами](manage-indicators.md)
