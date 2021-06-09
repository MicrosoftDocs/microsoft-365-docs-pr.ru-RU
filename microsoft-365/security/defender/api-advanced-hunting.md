---
title: Microsoft 365 Защитник расширенный API охоты
description: Узнайте, как запускать расширенные запросы на охоту с Microsoft 365 API для Microsoft 365 Defender.
keywords: Advanced Hunting, API, api, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3ff62265783be846a95964164e372100fe1ef662
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769590"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender Advanced hunting API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

[Расширенный поиск](advanced-hunting-overview.md) — это средство [](advanced-hunting-query-language.md) для охоты на угрозы, которое использует специально построенные запросы для изучения данных событий за последние 30 дней в Microsoft 365 Defender. Вы можете использовать расширенные запросы на охоту для проверки необычной активности, обнаружения возможных угроз и даже реагирования на атаки. Расширенный API охоты позволяет программным образом запрашивать данные событий.

## <a name="quotas-and-resource-allocation"></a>Квоты и распределение ресурсов

Следующие условия относятся к всем запросам.

1. Запросы исследуют и возвращают данные за последние 30 дней.
2. Результаты могут возвращать до 100 000 строк.
3. Вы можете сделать до 15 вызовов в минуту на каждого клиента.
4. Запросы блокируют, если клиент достиг 100% до следующего 15-минутного цикла.
5. Если один запрос выполняется более 10 минут, он будет время и возвращает ошибку.
6. Код ответа HTTP указывает, что вы достигли квоты либо по количеству отправленных запросов, либо по `429` выделенной продолжительной работе. Ознакомьтесь с текстом ответа, чтобы понять достигнутое ограничение. 

> [!NOTE]
> Все квоты, перечисленные выше (например, 15 вызовов за мин), являются для каждого клиента размером. Эти квоты минимальны.

## <a name="permissions"></a>Разрешения

Одно из следующих разрешений необходимо для вызова продвинутого API охоты. Дополнительные возможности, в том числе выбор разрешений, см. в Microsoft 365 [API защиты защитника](api-access.md)

Тип разрешения | Разрешение | Имя отображения разрешений
-|-|-
Приложение | AdvancedHunting.Read.All | Запуск расширенных запросов
Делегированные (рабочая или учебная учетная запись) | AdvancedHunting.Read | Запуск расширенных запросов

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>
>- Пользователю должна быть роль AD "View Data"
>- Пользователь должен иметь доступ к устройству в зависимости от параметров группы устройств.

## <a name="http-request"></a>HTTP-запрос

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Заголовки запросов

Заголовок | Значение
-|-
Авторизация | Bearer {token} **Примечание: требуется**
Content-Type | application/json

## <a name="request-body"></a>Тело запроса

В теле запроса поставляем объект JSON со следующими параметрами:

Параметр | Тип | Описание
-|-|-
Запрос | Текст | Запрос для выполнения. **Примечание: требуется**

## <a name="response"></a>Отклик

В случае успешного выполнения этот метод `200 OK` возвращается и _объект QueryResponse_ в теле отклика.

Объект ответа содержит три свойства верхнего уровня:

1. Stats — словарь статистики производительности запросов.
2. Схема — схема ответа, список Name-Type для каждого столбца.
3. Результаты — список расширенных событий охоты.

## <a name="example"></a>Пример

В следующем примере пользователь отправляет запрос ниже и получает объект ответа API, содержащий `Stats` , `Schema` и `Results` .

### <a name="query"></a>Запрос

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>Объект response

```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
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
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}
```

## <a name="related-articles"></a>Связанные статьи

- [Доступ к API Microsoft 365 Defender](api-access.md)
- [Узнайте о ограничениях API и лицензировании](api-terms.md)
- [Понимание кодов ошибок](api-error-codes.md)
- [Обзор расширенной охоты](advanced-hunting-overview.md)
