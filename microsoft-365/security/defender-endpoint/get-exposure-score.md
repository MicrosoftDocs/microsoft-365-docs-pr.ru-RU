---
title: Получить показатель уязвимости
description: Извлекает оценку экспозиции организации.
keywords: apis, graph api, supported apis, get, exposure score, organizational exposure score
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: 071b0e7597d334fe06d5045e06a5c4d82dd65609
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845394"
---
# <a name="get-exposure-score"></a>Получить показатель уязвимости

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

Извлекает оценку экспозиции организации.

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения | Разрешение | Имя отображения разрешений
:---|:---|:---
Приложение | Score.Read.All | 'Read Threat and Vulnerability Management score'
Делегированные (рабочая или учебная учетная запись) | Score.Read | 'Read Threat and Vulnerability Management score'

## <a name="http-request"></a>HTTP-запрос

```
GET /api/exposureScore
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Авторизация | String | Bearer {token}. **Обязательное поле**.

## <a name="request-body"></a>Тело запроса

переменная Empty

## <a name="response"></a>Отклик

В случае успешной работы этот метод возвращает 200 ОК с данными экспозиции в теле отклика.

## <a name="example"></a>Пример

### <a name="request"></a>Запрос

Ниже приведен пример запроса.

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a>Отклик

Ниже приведен пример отклика.

>[!NOTE]
>Список ответов, показанный здесь, может быть усечен для краткости. 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a>См. также

- [Управление рисками & уязвимостей](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Оценка & уязвимости](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
