---
title: Создание модели
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Используйте REST API для создания модели и связанного типа контента.
ms.openlocfilehash: 1c5bd84c777774edc1aa0c2419181f7b84aa4707
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287249"
---
# <a name="create-model"></a>Создание модели

Создает модель и связанный тип контента. Обратите внимание, что при этом модель только создается. Ее по-прежнему потребуется обучить в центре контента (см. [пример](rest-createmodel-method.md#examples)).

## <a name="http-request"></a>HTTP-запрос

```http
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a>Параметры URI

None;

## <a name="request-headers"></a>Заголовки запросов

| Заголовок | Значение |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|Подходящий дайджест для текущего сайта|

## <a name="request-body"></a>Тело запроса

|Имя    |Тип   |Описание |
|--------|-------|------------|
|_metadata|  |Настройте метаданные объекта в SPO. Всегда используйте значение {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}. |
|ContentTypeGroup|строка|Связанная группа типов контента, относящаяся к модели. По умолчанию используется значение "Типы интеллектуального контента документа".|
|ContentTypeName|строка|Имя связанного типа контента. У созданного файла модели будет такое же имя.|

## <a name="responses"></a>Ответы

| Имя   | Тип  | Описание|
|--------|-------|------------|
|201 Создано| |Успешное выполнение|

## <a name="examples"></a>Примеры

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a>Создание новой модели осмысления документации под названием "Контракт Contoso"

#### <a name="sample-request"></a>Пример запроса

```json
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a>Пример отклика

**Код состояния:** 201

## <a name="see-also"></a>См. также

[REST API модели осмысления документации Syntex](syntex-model-rest-api.md)
