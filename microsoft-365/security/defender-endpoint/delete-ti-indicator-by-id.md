---
title: Удаление API индикатора.
description: Узнайте, как использовать API delete Indicator для удаления объекта индикатора по ID в Microsoft Defender для конечной точки.
keywords: apis, public api, supported apis, delete, ti indicator, entity, id
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
ms.openlocfilehash: 1541e1d6e177416d77d768cef04d2524e6907ab5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289923"
---
# <a name="delete-indicator-api"></a>Удаление API индикатора

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Описание API

Удаляет объект [индикатора](ti-indicator.md) по ID.

## <a name="limitations"></a>Ограничения

Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные новости, в том числе выбор разрешений, см. в [руб. Начало работы](apis-intro.md)

Тип разрешения | Разрешение | Имя отображения разрешений
:---|:---|:---
Application | Ti.ReadWrite | "Чтение и написание индикаторов TI"
Application | Ti.ReadWrite.All | 'Read and write Indicators'

## <a name="http-request"></a>HTTP-запрос

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Authorization | Строка | Bearer {token}. **Обязательное поле**.

## <a name="request-body"></a>Текст запроса

переменная Empty

## <a name="response"></a>Отклик

Если Индикатор существует и успешно удаляется — 204 ОК без контента.

Если индикатор с указанным id не найден - 404 Не найден.

## <a name="example"></a>Пример

### <a name="request"></a>Запрос

Ниже приведен пример запроса.

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
