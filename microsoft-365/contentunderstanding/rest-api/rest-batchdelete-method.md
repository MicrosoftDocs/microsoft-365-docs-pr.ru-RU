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
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904275"
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
|ModelUniqueId|да|строка|Уникальный идентификатор файла модели.|
TargetSiteUrl|да|строка|Полный URL-адрес сайта целевой библиотеки.|
TargetWebServerRelativeUrl|да|строка|Относительный URL-адрес сервера для веб-сайта целевой библиотеки.|
TargetLibraryServerRelativeUrl|да|строка|Относительный URL-адрес сервера целевой библиотеки.|
ViewOption|Нет|string|Указывает, следует ли установить новое представление модели в качестве библиотеки по умолчанию.|

## <a name="response"></a>Отклик

| Имя   | Тип  | Описание|
|--------|-------|------------|
|200 OK| |Успешное выполнение|


## <a name="examples"></a>Примеры

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>Удаление модели из библиотеки контрактных документов на сайте репозитория

В этом примере для модели осмысления документации контрактов Contoso используется ИД `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Пример запроса

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a>Пример отклика

В отклике параметры TotalFailures и TotalSuccesses указывают на количество сбоев и успешных выполнений модели, применяемой к указанным библиотекам.

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
