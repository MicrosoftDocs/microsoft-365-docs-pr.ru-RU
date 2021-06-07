---
title: Оценка экспозиции списка по группе устройств
description: Извлекает список результатов воздействия по группе устройств.
keywords: apis, graph api, supported apis, get, exposure score, device group, device group exposure score
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 71daccdbcb223ac48d80721bf0a296d9c1a7c98c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770101"
---
# <a name="list-exposure-score-by-device-group"></a>Оценка экспозиции списка по группе устройств

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Извлекает коллекцию оповещений, связанных с заданным доменным адресом.

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Приложение | Score.Read.All | 'Read Threat and Vulnerability Management score'
Делегированные (рабочая или учебная учетная запись) | Score.Read | 'Read Threat and Vulnerability Management score'

## <a name="http-request"></a>HTTP-запрос

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a>Заголовки запросов

| Имя        | Тип | Описание
|:--------------|:-------|:--------------|
| Authorization | String | Bearer {token}. **Обязательно**.

## <a name="request-body"></a>Текст запроса

переменная Empty

## <a name="response"></a>Отклик

В случае успешной работы этот метод возвращает 200 ОК со списком показателей экспозиции на данные группы устройств в теле отклика.

## <a name="example"></a>Пример

### <a name="request"></a>Запрос

Ниже приведен пример запроса.

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a>Отклик

Ниже приведен пример отклика.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Связанные статьи

- [Управление рисками & уязвимостей](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Оценка & уязвимости](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
