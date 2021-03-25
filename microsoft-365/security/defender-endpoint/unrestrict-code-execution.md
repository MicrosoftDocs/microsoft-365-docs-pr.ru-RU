---
title: Удаление API ограничений приложений
description: Используйте этот API для создания вызовов, связанных с удалением ограничения из приложений при выполнении.
keywords: apis, api графа, поддерживаемые apis, удаление устройства из изоляции
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
ms.technology: mde
ms.openlocfilehash: abff4e02bfdfe6f5598ca96121815930dce3c85e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199325"
---
# <a name="remove-app-restriction-api"></a>Удаление API ограничений приложений

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Описание API
Включить выполнение любого приложения на устройстве.


## <a name="limitations"></a>Ограничения
1. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Application |   Machine.RestrictExecution | "Ограничение выполнения кода"
Делегированное (рабочая или учебная учетная запись) | Machine.RestrictExecution | "Ограничение выполнения кода"

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>- У пользователя должно быть по крайней мере следующее разрешение на роль: "Активные действия по исправлению" (см. дополнительные сведения о создании и управлении ролями) [](user-roles.md)
>- Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).

## <a name="http-request"></a>HTTP-запрос
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unrestrictCodeExecution
```

## <a name="request-headers"></a>Заголовки запросов
Имя | Тип | Описание
:---|:---|:---
Авторизация | Строка | Bearer {token}. **Обязательное поле**.
Content-Type | string | application/json. **Обязательное поле**.

## <a name="request-body"></a>Текст запроса
В теле запроса поставляем объект JSON со следующими параметрами:

Параметр | Тип    | Описание
:---|:---|:---
Comment |   String | Комментарий для связи с действием. **Обязательное поле**.

## <a name="response"></a>Отклик
В случае успешной работы этот метод возвращает 201 — созданный код ответа и действие машины [в](machineaction.md) тексте отклика.


## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unrestrictCodeExecution 
```

```json
{
  "Comment": "Unrestrict code execution since machine was cleaned and validated"
}

```


Чтобы ограничить выполнение кода на устройстве, см. [в приложении Restrict execution.](restrict-code-execution.md)
