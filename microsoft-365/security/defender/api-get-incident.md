---
title: Получить API инцидентов
description: Узнайте, как использовать API get incidents для получения одного инцидента в Microsoft 365 Defender.
keywords: apis, graph api, supported apis, get, file, hash
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
ms.openlocfilehash: c578a353501ac7b38ac541b0200ffaad1d6743e1
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888456"
---
# <a name="get-incident-information-api"></a>Получить API сведений об инцидентах

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Описание API
Извлечение определенного инцидента по его ID


## <a name="limitations"></a>Ограничения
1. Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.


## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. 

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Приложение |   Incident.Read.All | 'Read all Incidents'
Приложение |   Incident.ReadWrite.All |    'Read and write all Incidents'
Делегированные (рабочая или учебная учетная запись) | Incident.Read | 'Read Incidents'
Делегированные (рабочая или учебная учетная запись) | Incident.ReadWrite | 'Read and write Incidents'

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>- У пользователя должно быть по крайней мере следующее разрешение на роль: "Просмотр данных"
>- Ответ будет включать только инциденты, которые пользователь подвергается воздействию

## <a name="http-request"></a>HTTP-запрос

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Authorization | String | Bearer {token}. **Обязательное поле**.


## <a name="request-body"></a>Текст запроса
переменная Empty

## <a name="response"></a>Отклик

В случае успешной работы этот метод возвращает 200 ОК и объект инцидента в теле отклика. Если инцидент с указанным id не найден - 404 Не найден.

## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
