---
title: Список устройств по программному обеспечению
description: Извлечение списка устройств, на которые установлено это программное обеспечение.
keywords: apis, graph api, supported apis, get, list devices, devices list devices by software, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: e1adf28823d6b86417c32578a89480958946c50d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770569"
---
# <a name="list-devices-by-software"></a>Список устройств по программному обеспечению

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Извлечение списка ссылок на устройства с установленным программным обеспечением.

## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Приложение | Software.Read.All | 'Read Threat and Vulnerability Management Software information'
Делегированные (рабочая или учебная учетная запись) | Software.Read | 'Read Threat and Vulnerability Management Software information'

## <a name="http-request"></a>HTTP-запрос
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a>Заголовки запросов

| Имя        | Тип | Описание
|:--------------|:-------|:--------------|
| Authorization | String | Bearer {token}. **Обязательно**.

## <a name="request-body"></a>Текст запроса
переменная Empty

## <a name="response"></a>Отклик
В случае успеха этот метод возвращает 200 ОК и список устройств с программным обеспечением, установленным в теле. 


## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

**Отклик**

Ниже приведен пример отклика.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Связанные статьи
- [Управление рисками & уязвимостей](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Инвентаризация программного обеспечения & уязвимости](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
