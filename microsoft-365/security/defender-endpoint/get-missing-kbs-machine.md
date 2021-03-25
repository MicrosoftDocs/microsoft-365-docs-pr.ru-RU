---
title: Отсутствие KBs по ID устройства
description: Извлечение отсутствующих обновлений безопасности по ID устройства
keywords: apis, api graph, supported apis, get, list, file, information, device id, threat & vulnerability management api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 908ddf531a5a20b9811084ba534a152ad6158170
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198853"
---
# <a name="get-missing-kbs-by-device-id"></a>Отсутствие KBs по ID устройства

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Извлечение отсутствующих КБ (обновлений безопасности) по ID устройства

## <a name="http-request"></a>HTTP-запрос

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a>Заготвка запроса

Имя | Тип | Описание
:---|:---|:---
Авторизация | Строка | Bearer {token}. **Обязательное поле**.

## <a name="request-body"></a>Текст запроса

переменная Empty

## <a name="response"></a>Отклик

В случае успешной работы этот метод возвращает 200 ОК, при этом указанному устройству отсутствуют данные kb в теле.

## <a name="example"></a>Пример

### <a name="request"></a>Запрос

Ниже приведен пример запроса.

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a>Отклик

Ниже приведен пример отклика.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        },
         ...
        ]
}
```

## <a name="related-topics"></a>Статьи по теме

- [Управление рисками & уязвимостей](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Инвентаризация программного обеспечения & уязвимости](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
