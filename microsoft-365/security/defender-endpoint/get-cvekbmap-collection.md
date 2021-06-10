---
title: Получить API карты CVE-KB
description: Узнайте, как использовать API карты Get CVE-KB для получения карты CVE в сведениях KB и CVE в Microsoft Defender for Endpoint.
keywords: apis, api graph, supported apis, get, cve, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166891"
---
# <a name="get-cve-kb-map-api"></a>Получить API карты CVE-KB

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Извлекает карту CVE в сведения kB и CVE.

## <a name="permissions"></a>Разрешения
Пользователю нужны разрешения на чтение.

## <a name="http-request"></a>HTTP-запрос
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a>Заголовки запросов

Заголовок | Значение 
:---|:---
Авторизация | Bearer {token}. **Обязательное поле**.
Тип содержимого | application/json

## <a name="request-body"></a>Тело запроса
переменная Empty

## <a name="response"></a>Отклик
Если успешно и карта существует - 200 ОК.

## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

**Отклик**

Ниже приведен пример отклика.

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
