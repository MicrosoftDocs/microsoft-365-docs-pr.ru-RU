---
title: Расширенные API поисковых интерфейсов
description: Узнайте, как выполнять расширенные поисковые запросы с помощью API Microsoft Threat protection
keywords: Расширенный поиск, API, API, MTP
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: dd7b02200e370588bbb9470a3d7e897b30234ead
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197813"
---
# <a name="advanced-hunting-apis"></a>Расширенные API поисковых интерфейсов

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)

>[!IMPORTANT] 
>Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="limitations"></a>Ограничения
1. Запрос данных можно выполнить только за последние 30 дней.
2. В результаты будет включено не более 100 000 строк.
3. Количество выполнений ограничено для каждого клиента: до 10 вызовов в минуту, 10 минут времени выполнения в час и 4 часа выполнения в день.
4. Максимальное время выполнения одного запроса составляет 10 минут.
5. 429 ответ будет представлять предельную квоту либо по количеству запросов, либо по ЦП. Текст ответа 429 также будет указывать время до продления квоты. 


## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Дополнительные сведения, в том числе выбор разрешений, приведены [в статье Access API защиты от угроз Майкрософт](api-access.md)

Тип разрешения |   Разрешение  |   Отображаемое имя разрешения
:---|:---|:---
Приложение |   Адванцедхунтинг. Read. ALL |  "Выполнение расширенных запросов"
Делегированные (рабочая или учебная учетная запись) | Адванцедхунтинг. Read | "Выполнение расширенных запросов"

>[!Note]
> При получении маркера с использованием учетных данных пользователя:
>- Пользователь должен иметь роль AD "View Data"
>- Пользователь должен иметь доступ к устройству на основе параметров группы устройств.

## <a name="http-request"></a>HTTP-запрос
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Заголовки запросов

Заголовок | Значение 
:---|:---
Авторизация | Bearer {Token}. **Обязательное поле**.
Content-Type    | application/json

## <a name="request-body"></a>Текст запроса
В теле запроса добавьте объект JSON со следующими параметрами:

Параметр | Тип    | Описание
:---|:---|:---
Запрос | Текст |  Выполняемый запрос. **Обязательное поле**.

## <a name="response"></a>Отклик
В случае успешного выполнения этот метод возвращает 200 ОК и объект _куериреспонсе_ в тексте отклика. <br><br>

Объект Response разделен на 3 части (свойств):<br>
1) ```Stats``` — Статистика производительности запросов.<br>
2) ```Schema``` — Схема ответа, список пар "имя — тип" для каждого столбца. <br>
3) ```Results``` — Список событий расширенного поискового элемента.

## <a name="example"></a>Пример

Запрос

Ниже приведен пример запроса.


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

Отклик

Ниже приведен пример отклика.


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

## <a name="related-topic"></a>Связанная тема
- [Доступ к API защиты от угроз Майкрософт](api-access.md)
