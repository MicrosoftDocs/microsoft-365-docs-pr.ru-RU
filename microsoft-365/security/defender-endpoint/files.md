---
title: Тип ресурса file
description: Извлечение последних оповещений Microsoft Defender для конечных точек, связанных с файлами.
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.openlocfilehash: 9079a47dcc078b582586370b322502b74ce3838c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199985"
---
# <a name="file-resource-type"></a>Тип ресурса file

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Представляет объект файла в Защитнике для конечной точки.

## <a name="methods"></a>Методы
Метод|Возвращаемый тип |Описание
:---|:---|:---
[Получить файл](get-file-information.md) | [file](files.md) | Получить один файл 
[Оповещений, связанных с файлами списка](get-file-related-alerts.md) | Коллекция [alert](alerts.md) | Получите [объекты](alerts.md) оповещений, связанные с файлом.
[Машины, связанные с файлами списка](get-file-related-machines.md) | [коллекция](machine.md) машин | Получите [объекты](machine.md) машины, связанные с оповещением.
[статистика файлов](get-file-statistics.md) | Сводка статистики | Извлекает распространенность для данного файла.


## <a name="properties"></a>Свойства
|Свойство | Тип    |   Описание |
|:---|:---|:---|
|sha1 | Строка | Sha1 hash of the file content |
|sha256 | Строка | Sha256 hash of the file content |
|globalPrevalence | Nullable long | Распространенность файлов в организации |
|globalFirstObserved | DateTimeOffset | При первом наблюдении файла |
|globalLastObserved | DateTimeOffset | Последний раз, когда файл был замечен |
|size | Nullable long | Размер файла |
|fileType | Строка | Тип файла |
|isPeFile | Boolean | верно, если файл является переносным для выполнения (например, "DLL", "EXE" и т.д.) |
|filePublisher | Строка | Издатель файлов |
|fileProductName | Строка | Название продукта |
|подписывка | Строка | Подписатель файлов |
|эмитент | Строка | Эмитент файлов |
|signerHash | Строка | Hash of the signing certificate |
|isValidCertificate | Boolean | Был успешно проверен сертификат подписи агентом Microsoft Defender для конечных точек. |
|determinationType | Строка | Тип определения файла |
|determinationValue | Строка | Значение определения |


## <a name="json-representation"></a>Представление Json

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
