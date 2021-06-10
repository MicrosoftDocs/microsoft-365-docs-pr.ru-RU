---
title: API индикаторов импорта
description: Узнайте, как использовать импортную партию API индикатора в Microsoft Defender для конечной точки.
keywords: apis, поддерживаемые apis, отправка, ti, индикатор, обновление
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
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198249"
---
# <a name="import-indicators-api"></a>API индикаторов импорта

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Описание API
Отправка или обновление пакета [сущностями индикатора.](ti-indicator.md)
<br>Нотация CIDR для ИП не поддерживается.

## <a name="limitations"></a>Ограничения
1. Ограничения скорости для этого API — 30 вызовов в минуту.
2. Существует ограничение в 15 000 активных [индикаторов на](ti-indicator.md) одного клиента. 
3. Максимальный размер пакета для одного вызова API — 500.

## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные новости, в том числе выбор разрешений, см. в [руб. Начало работы](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Приложение |   Ti.ReadWrite |  'Read and write Indicators'
Приложение |   Ti.ReadWrite.All |  'Read and write All Indicators'
Делегированные (рабочая или учебная учетная запись) |    Ti.ReadWrite |  'Read and write Indicators'


## <a name="http-request"></a>HTTP-запрос
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Авторизация | String | Bearer {token}. **Обязательное поле**.
Content-Type | string | application/json. **Обязательное поле**.

## <a name="request-body"></a>Тело запроса
В теле запроса поставляем объект JSON со следующими параметрами:

Параметр | Тип    | Описание
:---|:---|:---
Индикаторы | Индикатор<[списка](ti-indicator.md)> | Список [индикаторов](ti-indicator.md). **Required**


## <a name="response"></a>Отклик
- В случае успешного результата этот метод возвращает код ответа 200 ОК со списком результатов импорта для каждого индикатора, см. в примере ниже.
- Если не удалось: этот метод возвращает 400 — Bad Request. Плохой запрос обычно указывает неправильное тело.

## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

**Отклик**

Ниже приведен пример отклика.

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a>Связанная тема
- [Управление индикаторами](manage-indicators.md)
