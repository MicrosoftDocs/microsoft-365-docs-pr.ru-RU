---
title: Получить рекомендации по программному обеспечению
description: Извлекает рекомендации по безопасности, связанные с определенным программным обеспечением.
keywords: apis, graph api, supported apis, get, security recommendation, security recommendation for software, контроль угроз и уязвимостей, контроль угроз и уязвимостей api
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
ms.openlocfilehash: 9227987544e1cee1eeb4b65b5ae6bbf719558dd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845214"
---
# <a name="get-recommendation-by-software"></a>Получить рекомендации по программному обеспечению

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

Извлекает рекомендации по безопасности, связанные с определенным программным обеспечением.

## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Для приложений |   SecurityRecommendation.Read.All |   'Read Threat and Vulnerability Management security recommendation information'
Делегированные (рабочая или учебная учетная запись) | SecurityRecommendation.Read |  'Read Threat and Vulnerability Management security recommendation information'

## <a name="http-request"></a>HTTP-запрос
```
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Authorization | String | Bearer {token}. **Обязательное поле**.


## <a name="request-body"></a>Тело запроса
переменная Empty

## <a name="response"></a>Отклик
В случае успеха этот метод возвращает 200 ОК с программным обеспечением, связанным с рекомендациями по безопасности в теле.


## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

**Отклик**

Ниже приведен пример отклика.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## <a name="related-topics"></a>Статьи по теме
- [Управление рисками & уязвимостей](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Рекомендация по & уязвимости](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
