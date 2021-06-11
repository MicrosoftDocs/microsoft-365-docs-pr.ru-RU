---
title: тип ресурса machineAction
description: Узнайте о методах и свойствах типа ресурсов MachineAction в Microsoft Defender for Endpoint.
keywords: apis, поддерживаемые apis, get, machineaction, последние
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
ms.openlocfilehash: a3b017a9a05964c15411668787b035f1052c68cf
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878284"
---
# <a name="machineaction-resource-type"></a>Тип ресурса MachineAction

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Дополнительные сведения см. в [дополнительных сведениях в ответных действиях.](respond-machine-alerts.md) 

| Метод                                                            | Возвращаемый тип                        | Описание                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [MachineActions списка](get-machineactions-collection.md)           | [Действие компьютера](machineaction.md) | Списки [сущностями](machineaction.md) действий машин.           |
| [Get MachineAction](get-machineaction-object.md)                  | [Действие компьютера](machineaction.md) | Получите одно [целое действие](machineaction.md) машины.     |
| [Сбор пакета исследования](collect-investigation-package.md) | [Действие компьютера](machineaction.md) | Сбор пакета исследований с [компьютера.](machine.md) |
| [Получить универсальный код ресурса (URI) SAS пакета исследования](get-package-sas-uri.md)       | [Действие компьютера](machineaction.md) | Получите URI для скачивания пакета исследований.          |
| [Изолировать компьютер](isolate-machine.md)                             | [Действие компьютера](machineaction.md) | Изолировать [машину](machine.md) от сети.                 |
| [Освобождение компьютера от изоляции](unisolate-machine.md)            | [Действие компьютера](machineaction.md) | Выпуск [машины из](machine.md) isolation.               |
| [Ограничить выполнение приложения](restrict-code-execution.md)              | [Действие компьютера](machineaction.md) | Ограничение выполнения приложения.                             |
| [Удалить ограничение приложения](unrestrict-code-execution.md)            | [Действие компьютера](machineaction.md) | Снимите ограничение на выполнение приложений.                   |
| [Запуск проверки на вирусы](run-av-scan.md)                              | [Действие компьютера](machineaction.md) | Запустите av-сканирование Защитник Windows (если применимо).    |
| [Отключение компьютера](offboard-machine-api.md)                       | [Действие компьютера](machineaction.md) | Offboard [machine](machine.md) from Microsoft Defender for Endpoint. |
| [Остановка и помещение на карантин файла](stop-and-quarantine-file.md)           | [Действие компьютера](machineaction.md) | Остановите выполнение файла на компьютере и удалите его.        |
| [Запуск ответа в прямом эфире](run-live-response.md)                     | [Действие компьютера](machineaction.md)  | Выполняет последовательность команд живого ответа на устройстве                       |
| [Получить результат ответа в прямом эфире](get-live-response-result.md) | Объект URL-адреса      | Извлекает определенную ссылку на результат загрузки командной команды в прямом эфире по индексу. |
|[Отмена действия машины](cancel-machine-action.md)                                | [Действие компьютера](machineaction.md)  | Отмена активного действия машины.                                            |

<br>

## <a name="properties"></a>Свойства

| Свойство            | Тип           | Описание                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Идентификатор                  | Guid           | Identity of the [Machine Actionentity.](machineaction.md)                                                                                                                                                     |
| type                | Перечисление           | Тип действия. Возможные значения: "RunAntiVirusScan", "Offboard", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" и "UnrestrictCodeExecution" |
| scope               | string         | Область действия. "Полный" или "Селективный" для изоляции, "Быстрый" или "Полный" для антивирусного сканирования.                                                                                                   |
| запросчик           | String         | Удостоверение лица, которое выполнило действие.                                                                                                                                                               |
| requestorComment    | String         | Комментарий, написанный при выдаче действия.                                                                                                                                                              |
| status              | Перечисление           | Текущее состояние команды. Возможные значения: "Ожидание", "InProgress", "Succeeded", "Failed", "TimeOut" и "Canceled".                                                                                 |
| machineId           | String         | ID [машины,](machine.md) на которой выполнено действие.                                                                                                                                              |
| machineId           | String         | Имя [машины,](machine.md) на которой выполнено действие.                                                                                                                                            |
| creationDateTimeUtc | DateTimeOffset | Дата и время создания действия.                                                                                                                                                                 |
| lastUpdateTimeUtc   | DateTimeOffset | Последняя дата и время обновления состояния действия.                                                                                                                                                     |
| relatedFileInfo     | Класс          | Содержит два свойства. ```fileIdentifier```строка, Enum ```fileIdentifierType``` с возможными значениями: "Sha1", "Sha256" и "Md5".                                                                         |



## <a name="json-representation"></a>Представление Json

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```
