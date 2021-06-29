---
title: Пакетное применение модели
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
description: Используйте REST API для применения модели осмысления документации к одной или нескольким библиотекам.
ms.openlocfilehash: 24ea9a480bc3ce5a7745857de17a6fab6ed97685
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177265"
---
# <a name="batch-apply-model"></a>Пакетное применение модели

Применяет (или синхронизирует) обученную модель осмысления документации к одной или нескольким библиотекам (см. [пример](rest-applymodel-method.md#examples)).

## <a name="http-request"></a>HTTP-запрос

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
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
|__metadata|да|строка|Настройте метаданные объекта в SPO. Всегда используйте значение {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.|
|Publications|Да|MachineLearningPublicationEntityData[]|Коллекция объектов MachineLearningPublicationEntityData, каждый из которых определяет модель и целевую библиотеку документов.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData
| Имя | Обязательный | Тип | Описание |
|--------|-------|--------|------------|
|ModelUniqueId|да|строка|Уникальный идентификатор файла модели.|
|TargetSiteUrl|да|строка|Полный URL-адрес сайта целевой библиотеки.|
|TargetWebServerRelativeUrl|да|строка|Относительный URL-адрес сервера для веб-сайта целевой библиотеки.|
|TargetLibraryServerRelativeUrl|да|строка|Относительный URL-адрес сервера целевой библиотеки.|
|ViewOption|Нет|string|Указывает, следует ли установить новое представление модели в качестве библиотеки по умолчанию.|

## <a name="response"></a>Отклик

| Имя   | Тип  | Описание|
|--------|-------|------------|
|201 Создано||Это настраиваемый API для поддержки применения модели к библиотекам с несколькими документами. В случае частичного успеха также может возвращаться отклик "201 создано" и вызывающей стороне необходимо проверить текст отклика, чтобы понять, применена ли модель к библиотеке документов.|

## <a name="response-body"></a>Текст отклика
| Имя   | Тип  | Описание|
|--------|-------|------------|
|TotalSuccesses|int|Общее количество успешных применений модели к библиотеке документов.|
|TotalFailures|int|Общее количество неудачных применений модели к библиотеке документов.|
|Сведения|MachineLearningPublicationResult[]|Коллекция объектов MachineLearningPublicationResult, каждый из которых определяет подробный результат применения модели к библиотеке документов.|

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

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a>Применение модели к библиотеке контрактных документов на сайте репозитория

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

**Код состояния:** 201

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>См. также

[REST API модели осмысления документации Syntex](syntex-model-rest-api.md)
