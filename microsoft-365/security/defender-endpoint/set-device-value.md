---
title: Набор API значения устройства
description: Узнайте, как указать значение устройства с помощью API Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, tags, machine tags
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 76df62243db837ec91819497980ff1de2295e3b6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498307"
---
# <a name="set-device-value-api"></a>Набор API значения устройства

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Описание API

Установите значение устройства определенной [машины.](machine.md)<br>
Дополнительные [сведения см. в](tvm-assign-device-value.md) добавлении значений устройства.

## <a name="limitations"></a>Ограничения

1. Вы можете размещать на устройствах последний раз в соответствии с настроенным периодом хранения.

2. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.


## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения |    Разрешение    |    Имя отображения разрешений
:---|:---|:---
Приложение |    Machine.ReadWrite.All |    'Read and write all machine information'
Делегированные (рабочая или учебная учетная запись) | Machine.ReadWrite | 'Read and write machine information'

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>
>- У пользователя должно быть по крайней мере следующее разрешение на роль: "Управление параметром безопасности". Дополнительные сведения (см. [дополнительные сведения](user-roles.md) о создании ролей и управлении ими)
>- Пользователь должен иметь доступ к машине на основе параметров группы машин (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) машин).

## <a name="http-request"></a>HTTP-запрос

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Authorization | String | Bearer {token}. **Обязательное поле**.
Content-Type | string | application/json. **Обязательное поле**.

## <a name="request-body"></a>Текст запроса

В теле запроса поставляем объект JSON со следующими параметрами:

Параметр |    Тип    | Описание
:---|:---|:---
DeviceValue |    Перечисление |    Значение устройства. Допустимые значения: "Нормальный", "Низкий" и "Высокий". **Обязательное поле**.

## <a name="response"></a>Отклик

В случае успешной работы этот метод возвращает код ответа 200 — Ok и обновленный компьютер в тексте отклика.

## <a name="example"></a>Пример

**Запрос**

Вот пример запроса, который добавляет тег машины.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
