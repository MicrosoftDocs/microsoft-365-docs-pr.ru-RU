---
title: Запуск команд живого ответа на устройстве
description: Узнайте, как запустить последовательность команд живого ответа на устройстве.
keywords: apis, graph api, поддерживаемые apis, отправка в библиотеку
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879764"
---
#  <a name="run-live-response-commands-on-a-device"></a>Запуск команд живого ответа на устройстве

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Описание API

Выполняет последовательность команд живого ответа на устройстве

## <a name="limitations"></a>Ограничения

1.  Ограничения скорости для этого API : 10 вызовов в минуту (дополнительные запросы отвечают http 429).

2.  25 одновременно запущенных сеансов (запросы, превышающие ограничение регулирования, получат ответ "429 - слишком много запросов").

3.  Если машина недоступна, сеанс будет стоять в очереди до 3 дней.

4.  Время ото дня команд runScript через 10 минут.

5.  При сбойе команды живого ответа все последующие действия не будут выполнены.

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Подробнее, в том числе о выборе разрешений, см. в [руб. Начало работы.](apis-intro.md)

| Тип разрешения                    | Разрешение           | Имя отображения разрешений                   |
|------------------------------------|----------------------|-------------------------------------------|
| Приложение                        | Machine.LiveResponse | Запуск ответа в прямом эфире на определенном компьютере |
| Делегированные (рабочая или учебная учетная запись) | Machine.LiveResponse | Запуск ответа в прямом эфире на определенном компьютере |

## <a name="http-request"></a>HTTP-запрос

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a>Заголовки запросов

| Имя      | Тип | Описание                 |
|---------------|----------|---------------------------------|
| Authorization | String   | Bearer\<token>\. Обязательно.   |
| Content-Type  | string   | application/json. Обязательный. |

## <a name="request-body"></a>Текст запроса

| Параметр | Тип | Описание                                                        |
|---------------|----------|------------------------------------------------------------------------|
| Comment       | String   | Комментарий для связи с действием.                                 |
| Команды      | Массив    | Команды для запуска. Допустимые значения: PutFile, RunScript, GetFile. |

Команды:

| Тип команды | Параметры                                                                          | Описание                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| PutFile      | Клавиша: FileName  <br><br>  Значение: \<file name\>                                                                          | Помещает файл из библиотеки на устройство. Файлы сохраняются в рабочей папке и удаляются при перезапуске устройства по умолчанию.
| RunScript    | Key: ScriptName<br>Значение: \<Script from library\> <br><br> Key: Args  <br> Значение: \<Script arguments\>                          | Запускает скрипт из библиотеки на устройстве.    <br><br>  Параметр Args передается в скрипт. <br><br> Время ото дня через 10 минут.     
| GetFile      | Ключ. Путь <br> Значение: \<File path\>                                                        | Сбор файла с устройства. ПРИМЕЧАНИЕ. Необходимо избежать отщепок на пути.                                                                      |

## <a name="response"></a>Отклик

-   В случае успеха этот метод возвращает 200, Ок.
    Сущность действия. Если машина с указанным ИД не найдена - 404 Не найдено.

## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
**JSON**

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

**Отклик**

Ниже приведен пример отклика.

```HTTP
HTTP/1.1 200 Ok
```

Тип контента: приложение/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a>Статьи по теме
- [Получите API действий машины](get-machineaction-object.md)
- [Получить результат ответа в прямом эфире](get-live-response-result.md)
- [Отмена действия машины](cancel-machine-action.md)
