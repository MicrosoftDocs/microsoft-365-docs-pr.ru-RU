---
title: Список уязвимостей по рекомендациям
description: Извлекает список уязвимостей, связанных с рекомендацией по безопасности.
keywords: apis, graph api, supported apis, get, list of vulnerabilities, security recommendation, security recommendation for vulnerabilities, контроль угроз и уязвимостей, контроль угроз и уязвимостей api
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
ms.openlocfilehash: 8fc9bb53fd2cfe768710129704c13ee751a695a2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770449"
---
# <a name="list-vulnerabilities-by-recommendation"></a>Список уязвимостей по рекомендациям

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Извлекает список уязвимостей, связанных с рекомендацией по безопасности.

## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Приложение |   SecurityRecommendation.Read.All |   'Read Threat and Vulnerability Management security recommendation information'
Делегированные (рабочая или учебная учетная запись) | SecurityRecommendation.Read |  'Read Threat and Vulnerability Management security recommendation information'

## <a name="http-request"></a>HTTP-запрос
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Authorization | String | Bearer {token}. **Обязательное поле**.


## <a name="request-body"></a>Текст запроса
переменная Empty

## <a name="response"></a>Отклик
В случае успешной работы этот метод возвращает 200 ОК со списком уязвимостей, связанных с рекомендацией по безопасности.


## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

**Отклик**

Ниже приведен пример отклика.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-13748",
            "name": "CVE-2019-13748",
            "description": "Insufficient policy enforcement in developer tools in Google Chrome prior to 79.0.3945.79 allowed a local attacker to obtain potentially sensitive information from process memory via a crafted HTML page.",
            "severity": "Medium",
            "cvssV3": 6.5,
            "exposedMachines": 0,
            "publishedOn": "2019-12-10T00:00:00Z",
            "updatedOn": "2019-12-16T12:15:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
        ...
     ]
}
```

## <a name="related-topics"></a>Связанные статьи
- [Управление рисками & уязвимостей](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Рекомендация по & уязвимости](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
