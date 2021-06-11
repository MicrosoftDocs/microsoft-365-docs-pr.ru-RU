---
title: Получения результатов живого ответа
description: Узнайте, как получить определенный результат командной команды в прямом эфире по индексу.
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
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879787"
---
#  <a name="get-live-response-results"></a>Получения результатов живого ответа

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Описание API

Извлекает определенный результат команды живого ответа по индексу.

## <a name="limitations"></a>Ограничения

1.  Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Подробнее, в том числе о выборе разрешений, см. в [руб. Начало работы.](apis-intro.md)

| Тип разрешения                    | Разрешение           | Имя отображения разрешений                   |
|------------------------------------|----------------------|-------------------------------------------|
| Приложение                        | Machine.LiveResponse | Запуск ответа в прямом эфире на определенном компьютере |
| Делегированные (рабочая или учебная учетная запись) | Machine.LiveResponse | Запуск ответа в прямом эфире на определенном компьютере |

## <a name="http-request"></a>HTTP-запрос

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a>Заголовки запросов

| Имя      | Тип | Описание               |
|---------------|----------|-------------------------------|
| Authorization | String   | Bearer {токен}. Обязательный. |

## <a name="request-body"></a>Текст запроса

переменная Empty

## <a name="response"></a>Отклик

В случае успешного результата этот метод возвращает код ответа 200 Ok с объектом, который содержит ссылку на команду, приводит к свойству *значения.* Эта ссылка действительна в течение 30 минут и должна быть немедленно использована для скачивания пакета в локальное хранилище. Просроченная ссылка может быть повторно создана другим вызовом, и нет необходимости повторно запускать живой ответ.

*Свойства транскрипта runscript:*

| Свойство  | Описание                       |
|---------------|---------------------------------------|
| name          | Имя исполняемой скрипта                  |
| exit_code     | Выполненный код выхода скрипта             |
| script_output | Выполнение стандартных выходных данных сценариев       |
| script_error  | Выполнение стандартных выходных ошибок скрипта |

## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

**Отклик**

Ниже приведен пример отклика.

HTTP/1.1 200 Ok

Тип контента: приложение/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

*Содержимое файла:* 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a>Статьи по теме

- [Получите API действий машины](get-machineaction-object.md)
- [Отмена действия машины](cancel-machine-action.md)
- [Запуск ответа в прямом эфире](run-live-response.md) 
