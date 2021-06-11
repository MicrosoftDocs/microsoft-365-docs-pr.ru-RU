---
title: Отмена API действий машины
description: Узнайте, как отменить действие уже запущенной машины
keywords: apis, graph api,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879800"
---
#   <a name="cancel-machine-action-api"></a>Отмена API действий машины 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Описание API

Отмена уже запущенного действия машины, которое еще не в окончательном состоянии (завершено, отменено, не выполнено).

## <a name="limitations"></a>Ограничения

1.  Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Подробнее, в том числе о выборе разрешений, см. в [руб. Начало работы.](apis-intro.md)

|     Тип разрешения     |     Разрешение     |    Имя отображения разрешений     |
|-|-|-|
|    <br>Приложение    |    <br>Machine.CollectForensic<br>   Machine.Isolate   <br>Machine.RestrictExecution<br>   Machine.Scan<br>   Machine.Offboard<br>   Machine.StopAndQuarantine<br>   Machine.LiveResponse    |    Сбор криминалистической экспертизы   <br>Изолировать машину<br>Ограничение выполнения кода<br>  Машина сканирования<br>  Offboard machine<br>   Остановка и карантин<br>   Запуск ответа в прямом эфире на определенном компьютере    |
|    <br>Делегированная (работа или учетная запись школы)    |    Machine.CollectForensic<br>   Machine.Isolate    <br>Machine.RestrictExecution<br>   Machine.Scan<br>   Machine.Offboard<br>   Machine.StopAndQuarantineMachine.LiveResponse    |    Сбор криминалистической экспертизы<br>   Изолировать машину<br>  Ограничение выполнения кода<br> Машина сканирования<br>Offboard machine<br> Остановка и карантин<br> Запуск ответа в прямом эфире на определенном компьютере    |


## <a name="http-request"></a>HTTP-запрос

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a>Заголовки запросов

| Имя      | Тип | Описание                 |
|---------------|----------|---------------------------------|
| Authorization | String   | Bearer {токен}. Обязательный.   |
| Content-Type  | string   | application/json. Обязательный. |

## <a name="request-body"></a>Текст запроса

| Параметр | Тип | Описание                        |
|---------------|----------|----------------------------------------|
| Comment       | String   | Комментарий для связи с действием отмены.  |

## <a name="response"></a>Отклик

В случае успешной работы этот метод возвращает код ответа 200 Ok с объектом Machine Action. Если объект действия машины с указанным id не найден - 404 Не найден.

## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a>Связанная тема

- [Получите API действий машины](get-machineaction-object.md)