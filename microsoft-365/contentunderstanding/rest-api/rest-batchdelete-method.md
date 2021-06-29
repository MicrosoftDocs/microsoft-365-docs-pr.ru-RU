---
title: BatchDelete
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
description: Используйте REST API, чтобы удалить примененную модель осмысления документации из одной или нескольких библиотек.
ms.openlocfilehash: e95c0583b1b0e2f5de08228afbf161c339544047
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177241"
---
# <a name="batchdelete"></a>BatchDelete

Удаляет примененную модель осмысления документации из одной или нескольких библиотек. Обратите внимание, что перед удалением модели необходимо удалить ее из всех библиотек (см. [пример](rest-batchdelete-method.md#examples)).

## <a name="http-request"></a>HTTP-запрос

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a>Параметры URI

None;

## <a name="request-headers"></a>Заголовки запросов

| Заголовок | Значение |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|Подходящий дайджест для текущего сайта.|

## <a name="request-body"></a>Текст запроса

| Имя | Обязательный | Тип | Описание |
|--------|-------|--------|------------|
|Publications|Да|MachineLearningPublicationEntityData[]|Коллекция объектов MachineLearningPublicationEntityData, каждый из которых определяет модель и целевую библиотеку документов.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData
| Имя | Обязательный | Тип | Описание |
|--------|-------|--------|------------|
|ModelUniqueId|да|строка|Уникальный идентификатор файла модели.|
|TargetSiteUrl|да|строка|Полный URL-адрес сайта целевой библиотеки.|
|TargetWebServerRelativeUrl|да|строка|Относительный URL-адрес сервера для веб-сайта целевой библиотеки.|
|TargetLibraryServerRelativeUrl|да|строка|Относительный URL-адрес сервера целевой библиотеки.|

## <a name="response"></a>Отклик

| Имя   | Тип  | Описание|
|--------|-------|------------|
|200 OK||Это настраиваемый API для поддержки удаления модели из библиотек с несколькими документами. В случае частичного успеха также может возвращаться отклик 200 OK и вызывающей стороне необходимо проверить текст отклика, чтобы понять, удалена ли модель из библиотеки документов.|

## <a name="response-body"></a>Текст отклика
| Имя   | Тип  | Описание|
|--------|-------|------------|
|TotalSuccesses|int|Общее количество успешных удалений модели из библиотеки документов.|
|TotalFailures|int|Общее количество неудачных удалений модели из библиотеки документов.|
|Сведения|MachineLearningPublicationResult[]|Коллекция объектов MachineLearningPublicationResult, каждый из которых определяет подробный результат удаления модели из библиотеки документов.|

### <a name="machinelearningpublicationresult"></a>MachineLearningPublicationResult
| Имя   | Тип  | Описание|
|--------|-------|------------|
|StatusCode|int|Код состояния HTTP.|
|ErrorMessage|строка|Сообщение об ошибке, уведомляющее о проблемах при применении модели к библиотеке документов.|
|Publication|MachineLearningPublicationEntityData|Указывает сведения о модели и целевую библиотеку документов.| 

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData
| Имя | Тип | Описание |
|--------|--------|------------|
|ModelUniqueId|строка|Уникальный идентификатор файла модели.|
|TargetSiteUrl|строка|Полный URL-адрес сайта целевой библиотеки.|
|TargetWebServerRelativeUrl|строка|Относительный URL-адрес сервера для веб-сайта целевой библиотеки.|
|TargetLibraryServerRelativeUrl|строка|Относительный URL-адрес сервера целевой библиотеки.|

## <a name="examples"></a>Примеры

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>Удаление модели из библиотеки контрактных документов на сайте репозитория

В этом примере для модели осмысления документации контрактов Contoso используется ИД `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Пример запроса

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```


#### <a name="sample-response"></a>Пример отклика

В отклике параметры TotalFailures и TotalSuccesses указывают на количество неудачных и успешных удалений модели из указанных библиотек.

**Код состояния:** 200

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>См. также

[REST API модели осмысления документации Syntex](syntex-model-rest-api.md)
