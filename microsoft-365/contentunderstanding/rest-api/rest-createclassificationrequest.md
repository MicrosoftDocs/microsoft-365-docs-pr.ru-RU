---
title: Создание запроса классификации
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
description: Используйте REST API для создания запроса на классификацию одного или нескольких файлов с помощью обученной модели осмысления документации.
ms.openlocfilehash: b1022787d6e11ebe36c88ecd29936a777289dd74
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287237"
---
# <a name="create-classification-request"></a>Создание запроса классификации

Создает запрос на классификацию одного или нескольких файлов с помощью примененной модели осмысления документации (см. [пример](rest-createclassificationrequest.md#examples)).

Служба REST в SharePoint Online (а также локальной среде SharePoint 2016 или более поздней версии) поддерживает объединение нескольких запросов. Запросы объединяются в один вызов службы с помощью параметра запроса $batch OData. Этот метод можно использовать для одновременной постановки в очередь рабочих элементов классификации для сотен документов.

## <a name="http-request"></a>HTTP-запрос

```http
POST /_api/machinelearning/workItems HTTP/1.1
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
|_metadata|строка |Настройте метаданные объекта в SPO. Всегда используйте значение {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}. |
|TargetSiteId|guid|ИД сайта, на котором расположен файл для классификации.|
|TargetWebId|guid|ИД веб-сайта, на котором расположен файл для классификации.|
|TargetUniqueId|guid|ИД файла для классификации.|

## <a name="responses"></a>Ответы

| Имя   | Тип  | Описание|
|--------|-------|------------|
|201 Создано| |Успешное выполнение|

## <a name="examples"></a>Примеры

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>Постановка в очередь запроса на классификацию файла с ИД "e6cff8b7-c90c-4564-b5b8-033449090932"

#### <a name="sample-request"></a>Пример запроса

```JSON
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a>Пример отклика

**Код состояния:** 201

## <a name="see-also"></a>См. также

[REST API модели осмысления документации Syntex](syntex-model-rest-api.md)
