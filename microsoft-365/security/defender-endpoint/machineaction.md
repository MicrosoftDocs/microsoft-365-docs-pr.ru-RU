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
ms.openlocfilehash: da3722294957593fc9cb89abfaec13e45106eefc
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187389"
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
| [MachineActions списка](get-machineactions-collection.md)           | [Действие машины](machineaction.md) | Списки [сущностями](machineaction.md) действий машин.           |
| [Get MachineAction](get-machineaction-object.md)                  | [Действие машины](machineaction.md) | Получите одно [целое действие](machineaction.md) машины.     |
| [Сбор пакета расследований](collect-investigation-package.md) | [Действие машины](machineaction.md) | Сбор пакета исследований с [компьютера.](machine.md) |
| [Получить пакет исследований SAS URI](get-package-sas-uri.md)       | [Действие машины](machineaction.md) | Получите URI для скачивания пакета исследований.          |
| [Изолировать машину](isolate-machine.md)                             | [Действие машины](machineaction.md) | Изолировать [машину](machine.md) от сети.                 |
| [Освобождение машины из изоляции](unisolate-machine.md)            | [Действие машины](machineaction.md) | Выпуск [машины из](machine.md) isolation.               |
| [Ограничение выполнения приложения](restrict-code-execution.md)              | [Действие машины](machineaction.md) | Ограничение выполнения приложения.                             |
| [Удаление ограничения приложения](unrestrict-code-execution.md)            | [Действие машины](machineaction.md) | Снимите ограничение на выполнение приложений.                   |
| [Запуск антивирусного сканирования](run-av-scan.md)                              | [Действие машины](machineaction.md) | Запустите av-сканирование Защитник Windows (если применимо).    |
| [Offboard machine](offboard-machine-api.md)                       | [Действие машины](machineaction.md) | Offboard [machine](machine.md) from Microsoft Defender for Endpoint. |
| [Файл Стоп и карантин](stop-and-quarantine-file.md)           | [Действие машины](machineaction.md) | Остановите выполнение файла на компьютере и удалите его.        |

<br>

## <a name="properties"></a>Свойства

| Свойство            | Тип           | Описание                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Идентификатор                  | Guid           | Identity of the [Machine Actionentity.](machineaction.md)                                                                                                                                                     |
| type                | Перечисление           | Тип действия. Возможные значения: "RunAntiVirusScan", "Offboard", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" и "UnrestrictCodeExecution" |
| scope               | string         | Область действия. "Полный" или "Селективный" для изоляции, "Быстрый" или "Полный" для антивирусного сканирования.                                                                                                   |
| запросчик           | Строка         | Удостоверение лица, которое выполнило действие.                                                                                                                                                               |
| requestorComment    | Строка         | Комментарий, написанный при выдаче действия.                                                                                                                                                              |
| status              | Перечисление           | Текущее состояние команды. Возможные значения: "Ожидание", "InProgress", "Succeeded", "Failed", "TimeOut" и "Canceled".                                                                                 |
| machineId           | Строка         | ID [машины,](machine.md) на которой выполнено действие.                                                                                                                                              |
| machineId           | Строка         | Имя [машины,](machine.md) на которой выполнено действие.                                                                                                                                            |
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
