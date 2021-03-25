---
title: Программный интерфейс расширенной охоты
ms.reviewer: ''
description: Узнайте, как использовать расширенный API охоты для запуска расширенных запросов в Microsoft Defender для конечной точки. Узнайте об ограничениях и см. пример.
keywords: apis, поддерживаемый apis, расширенный поиск, запрос
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
ms.openlocfilehash: caf7a1bacfd726c560356d542bec3cf56c6b39d4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200201"
---
# <a name="advanced-hunting-api"></a>Расширенный API охоты

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a>Ограничения
1. Запрос по данным можно выполнить только за последние 30 дней.
2. Результаты будут включать не более 100 000 строк.
3. Количество исполняемой работы ограничено для каждого клиента:
   - Вызовы API: до 45 вызовов в минуту.
   - Время выполнения: 10 минут времени работы каждый час и 3 часа в день.
4. Максимальное время выполнения одного запроса — 10 минут.
5. Ответ 429 будет представлять достижение ограничения квоты по количеству запросов или по ЦП. Прочитайте текст ответа, чтобы понять, какой предел был достигнут. 

## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Application |   AdvancedQuery.Read.All |    'Run advanced queries'
Делегированное (рабочая или учебная учетная запись) | AdvancedQuery.Read | 'Run advanced queries'

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>- Пользователю должна быть роль AD "Просмотр данных"
>- Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).

## <a name="http-request"></a>HTTP-запрос
```
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a>Заголовки запросов

Заголовок | Значение 
:---|:---
Авторизация | Bearer {token}. **Обязательное поле**.
Content-Type    | application/json

## <a name="request-body"></a>Текст запроса
В теле запроса поставляем объект JSON со следующими параметрами:

Параметр | Тип    | Описание
:---|:---|:---
Запрос | Текст |  Запрос для выполнения. **Обязательное поле**.

## <a name="response"></a>Отклик
В случае успешного выполнения этот метод возвращает 200 ОК и _объект QueryResponse_ в теле отклика.


## <a name="example"></a>Пример

Запрос

Ниже приведен пример запроса.

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

Отклик

Ниже приведен пример отклика.

>[!NOTE]
>Показанный здесь объект ответа может быть усечен для краткости. При фактическом вызове будут возвращены все свойства.

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topic"></a>Связанная тема
- [Microsoft Defender для внедрения API конечных точек](apis-intro.md)
- [Расширенный поиск с портала](advanced-hunting-query-language.md)
- [Расширенный метод охоты с помощью PowerShell](run-advanced-query-sample-powershell.md)
