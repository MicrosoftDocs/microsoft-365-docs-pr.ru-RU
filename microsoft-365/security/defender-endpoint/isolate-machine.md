---
title: API изолированной машины
description: Узнайте, как использовать API машины Isolate для изоляции устройства от доступа к внешней сети в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, isolate device
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9f3313a08b072f4fb2f699148ab801207e56fc09
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772120"
---
# <a name="isolate-machine-api"></a>API изолированной машины

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Описание API
Изолирует устройство от доступа к внешней сети.


## <a name="limitations"></a>Ограничения
1. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Приложение |   Machine.Isolate |   'Isolate machine'
Делегированные (рабочая или учебная учетная запись) | Machine.Isolate |  'Isolate machine'

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>- У пользователя должно быть по крайней мере следующее разрешение на роль: "Активные действия по исправлению" (см. дополнительные сведения о создании и управлении ролями) [](user-roles.md)
>- Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).


## <a name="http-request"></a>HTTP-запрос
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Авторизация | String | Bearer {token}. **Обязательное поле**.
Content-Type | string | application/json. **Обязательное поле**.

## <a name="request-body"></a>Тело запроса
В теле запроса поставляем объект JSON со следующими параметрами:

Параметр | Тип    | Описание
:---|:---|:---
Comment |   String |    Комментарий для связи с действием. **Обязательное поле**.
IsolationType   | String |  Тип изоляции. Допустимые значения: "Полный" или "Селективный".

**IsolationType** управляет типом изоляции для выполнения и может быть одним из следующих:
- Полный — полная изоляция
- Селективный выбор : Ограничить доступ к сети только ограниченному набору приложений (дополнительные сведения см. в материале [Isolate devices from the network).](respond-machine-alerts.md#isolate-devices-from-the-network)


## <a name="response"></a>Отклик
В случае успешной работы этот метод возвращает 201 — созданный код ответа и действие машины [в](machineaction.md) тексте отклика.


## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- Чтобы освободить устройство от изоляции, см. в выпуске устройства [из изоляции.](unisolate-machine.md)
