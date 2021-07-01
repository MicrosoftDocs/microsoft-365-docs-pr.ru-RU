---
title: Получить API машин, связанных с пользователем
description: Узнайте, как использовать API машин get user-related для получения коллекции устройств, связанных с пользовательским ИД в Microsoft Defender for Endpoint.
keywords: apis, graph api, supported apis, get, user, user related alerts
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
ms.openlocfilehash: ead0558bfff90c29ec8717fbb39876afda5c42af
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229459"
---
# <a name="get-user-related-machines-api"></a>Получить API машин, связанных с пользователем

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Описание API
Извлекает коллекцию устройств, связанных с данным пользовательским ИД.

## <a name="limitations"></a>Ограничения

Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения |Разрешение|Имя отображения разрешений
:---|:---|:---
Приложение |Machine.Read.All|'Read all machine profiles'
Приложение |Machine.ReadWrite.All |'Read and write all machine information'
Делегированные (рабочая или учебная учетная запись) | Machine.Read | 'Read machine information'
Делегированные (рабочая или учебная учетная запись) | Machine.ReadWrite | 'Read and write machine information'

> [!NOTE]
> При получении маркера с помощью учетных данных пользователей:
>
> - У пользователя должно быть по крайней мере следующее разрешение на роль: "Просмотр данных". Дополнительные сведения см. в [дополнительных сведениях о создании и управлении ролями](user-roles.md))
> - Ответ будет включать только устройства, к которые пользователь может получить доступ, в зависимости от параметров группы устройств. Дополнительные сведения см. в [дополнительных сведениях о создании и управлении группами устройств.](machine-groups.md)

## <a name="http-request"></a>HTTP-запрос

```http
GET /api/users/{id}/machines
```

**ID — это не полное имя пользователя, а только имя пользователя. (например, для получения машин для user1@contoso.com /api/users/user1/machines)**

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Авторизация | String | Bearer {token}. **Обязательное поле**.

## <a name="request-body"></a>Текст запроса

переменная Empty

## <a name="response"></a>Отклик

При успешном и удобном пользователе — [](machine.md) 200 ОК со списком машинных сущностями в теле. Если пользователя не существует - 404 Не найдено.

## <a name="example"></a>Пример

### <a name="request"></a>Запрос

Ниже приведен пример запроса.

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
