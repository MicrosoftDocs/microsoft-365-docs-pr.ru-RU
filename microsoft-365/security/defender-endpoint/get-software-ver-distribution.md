---
title: Список распространения версий программного обеспечения
description: Извлечение списка распространения программной версии вашей организации
keywords: apis, graph api, supported apis, get, software version distribution, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7d0e38789cfc576c0c3f1a8be352796e674ac13a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845022"
---
# <a name="list-software-version-distribution"></a>Список распространения версий программного обеспечения 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Извлекает список распространения программной версии вашей организации. 

## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Приложение | Software.Read.All | 'Read Threat and Vulnerability Management Software information'
Делегированные (рабочая или учебная учетная запись) | Software.Read | 'Read Threat and Vulnerability Management Software information'

## <a name="http-request"></a>HTTP-запрос
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a>Заголовки запросов

| Имя        | Тип | Описание
|:--------------|:-------|:--------------|
| Авторизация | String | Bearer {token}. **Обязательно**.

## <a name="request-body"></a>Тело запроса
переменная Empty

## <a name="response"></a>Отклик
В случае успеха этот метод возвращает 200 ОК со списком данных о распространениях программного обеспечения в теле. 


## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

**Отклик**

Ниже приведен пример отклика.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Статьи по теме
- [Управление рисками & уязвимостей](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Инвентаризация программного обеспечения & уязвимости](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
