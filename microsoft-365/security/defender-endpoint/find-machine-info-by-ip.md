---
title: Поиск сведений о устройстве с помощью внутреннего API IP
description: Используйте этот API для создания вызовов, связанных с поиском записи устройства вокруг определенного времени с помощью внутреннего IP-адреса.
keywords: IP, apis, api graph, supported apis, find device, device information
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167143"
---
# <a name="find-device-information-by-internal-ip-api"></a>Поиск сведений о устройстве с помощью внутреннего API IP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Поиск устройства по внутреннему IP-адресу.

>[!NOTE]
>Время должно быть в течение последних 30 дней.

## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения | Разрешение | Имя отображения разрешений
:---|:---|:---
Приложение | Machine.Read.All | 'Read all machine profiles'
Приложение | Machine.ReadWrite.All | 'Read and write all machine information'

## <a name="http-request"></a>HTTP-запрос
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Авторизация | String | Bearer {token}. **Обязательное поле**.


## <a name="request-body"></a>Тело запроса
переменная Empty

## <a name="response"></a>Отклик
Если успешно и машина существует - 200 ОК.
Если машина не найдена - 404 Не найдено.


## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

**Отклик**

Ниже приведен пример отклика.

Ответ возвращает список всех устройств, которые сообщили об этом IP-адресе в течение шестнадцати минут до и после времени. 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
