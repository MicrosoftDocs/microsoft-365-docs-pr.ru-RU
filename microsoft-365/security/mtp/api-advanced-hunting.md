---
title: API расширенных охот на Microsoft 365 Defender
description: Узнайте, как запускать запросы на расширенный поиск с помощью API advanced hunting в Microsoft 365 Defender
keywords: Расширенный поиск, API, API, MTP, Защитник M365, Защитник Microsoft 365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 99f39a10de6231a72220c5c2a90ec915b1a4e44a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988120"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender Advanced hunting API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Защита от угроз (Майкрософт)

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

[Расширенный поиск](advanced-hunting-overview.md) — это средство [](advanced-hunting-query-language.md) охоты на угрозы, которое использует специально построенные запросы для изучения данных событий за последние 30 дней в Microsoft 365 Defender. Вы можете использовать расширенные поисковые запросы для проверки необычных действий, обнаружения возможных угроз и даже реагирования на атаки. API расширенных запросов позволяет программным образом запрашивать данные событий.

## <a name="quotas-and-resource-allocation"></a>Квоты и выделение ресурсов

Следующие условия относятся к всем запросам.

1. Запросы изучают и возвращают данные за последние 30 дней.
2. Результаты могут возвращать до 100 000 строк.
3. Вы можете делать до 15 вызовов в минуту на клиента.
4. У вас есть 10 минут времени работы в час на клиента.
5. Общее время работы на клиенте составляет четыре часа в день.
6. Если один запрос выполняется более 10 минут, время его времени и возвратит ошибку.
7. Код отклика HTTP указывает, что вы достигли квоты по количеству отправленных запросов или по выделению `429` времени работы. Прочитайте текст ответа, чтобы понять достигнутое ограничение. 

> [!NOTE]
> Все квоты, перечисленные выше (например, 15 вызовов на мин), имеют размер клиента. Эти квоты являются минимальными.

## <a name="permissions"></a>Permissions

Для вызова API advanced hunting требуется одно из следующих разрешений. Дополнительные возможности, включая выбор разрешений, см. в API Access для Защиты От защитника [Microsoft 365](api-access.md)

Тип разрешения | Разрешение | Отображаемая имя разрешения
-|-|-
Для приложений | AdvancedАting.Read.All | Выполнение расширенных запросов
Делегированные (рабочая или учебная учетная запись) | AdvancedАting.Read | Выполнение расширенных запросов

>[!Note]
> При получении маркера с использованием учетных данных пользователя:
>
>- Пользователю требуется роль AD "Просмотр данных"
>- Пользователь должен иметь доступ к устройству на основе параметров группы устройств.

## <a name="http-request"></a>HTTP-запрос

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Заголовки запросов

Заголовок | Значение
-|-
Authorization | Bearer {token} **Note: required**
Content-Type | application/json

## <a name="request-body"></a>Текст запроса

В теле запроса укажу объект JSON со следующими параметрами:

Параметр | Тип | Описание
-|-|-
Запрос | Текст | Запрос, который необходимо выполнить. **Примечание. обязательно**

## <a name="response"></a>Отклик

В случае успешного выполнения этот метод возвращает объект `200 OK` _QueryResponse_ в теле отклика.

Объект ответа содержит три свойства верхнего уровня:

1. Статистика — словарь статистики производительности запросов.
2. Схема — схема ответа, список Name-Type для каждого столбца.
3. Результаты — список событий расширенных охоты.

## <a name="example"></a>Пример

В следующем примере пользователь отправляет запрос ниже и получает объект ответа API, содержащий `Stats` , `Schema` и `Results` .

### <a name="query"></a>Запрос

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>Объект Response

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

## <a name="related-articles"></a>Статьи по теме

- [Доступ к API Microsoft 365 Defender](api-access.md)
- [Узнайте об ограничениях API и лицензировании](api-terms.md)
- [Коды ошибок](api-error-codes.md)
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
