---
title: UpdateModelSettings
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
description: Используйте REST API для обновления доступных параметров моделей осмысления документации SharePoint Syntex.
ms.openlocfilehash: f24fc8428adbf22ded2ca6d7a49cabc84b385770
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904305"
---
# <a name="updatemodelsettings"></a>UpdateModelSettings

Обновляет доступные параметры моделей (связанную метку хранения и описание модели) для модели осмысления документации SharePoint Syntex (см. [пример](rest-updatemodelsettings-method.md#examples)).

## <a name="http-request"></a>HTTP-запрос

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
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

|Имя    |Тип   |Описание |
|--------|-------|-------|
|ModelSettings|строка|Формат JSON параметров модели.|
|Описание|string|Описание модели.|
|RetentionLabel| |Сведения для связанной метки (ИД и имя метки).|

## <a name="responses"></a>Ответы

| Имя   | Тип  | Описание|
|--------|-------|------------|
|200 OK| |Успешное выполнение|

## <a name="examples"></a>Примеры

### <a name="update-model-settings-for-contoso-contract"></a>Обновление параметров модели для контрактов Contoso

В этом примере обновляется описание модели и метка хранения "Стандартное удержание". ИД метки хранения: `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.

#### <a name="sample-request"></a>Пример запроса

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a>Пример отклика

**Код состояния:** 200

## <a name="see-also"></a>См. также

[REST API модели осмысления документации Syntex](syntex-model-rest-api.md)
