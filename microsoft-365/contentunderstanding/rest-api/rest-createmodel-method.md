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
ms.openlocfilehash: 0a1b6ef9b7e38f2c4f52082103530da432e3e855
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177157"
---
# <a name="create-model"></a><span data-ttu-id="74319-103">Создание модели</span><span class="sxs-lookup"><span data-stu-id="74319-103">Create model</span></span>

<span data-ttu-id="74319-104">Создает модель и связанный тип контента.</span><span class="sxs-lookup"><span data-stu-id="74319-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="74319-105">Обратите внимание, что при этом модель только создается.</span><span class="sxs-lookup"><span data-stu-id="74319-105">Note that this only creates the model.</span></span> <span data-ttu-id="74319-106">Ее по-прежнему потребуется обучить в центре контента (см. [пример](rest-createmodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="74319-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="74319-107">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="74319-107">HTTP request</span></span>

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="74319-108">Параметры URI</span><span class="sxs-lookup"><span data-stu-id="74319-108">URI Parameters</span></span>

<span data-ttu-id="74319-109">None;</span><span class="sxs-lookup"><span data-stu-id="74319-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="74319-110">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="74319-110">Request headers</span></span>

| <span data-ttu-id="74319-111">Заголовок</span><span class="sxs-lookup"><span data-stu-id="74319-111">Header</span></span> | <span data-ttu-id="74319-112">Значение</span><span class="sxs-lookup"><span data-stu-id="74319-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="74319-113">Accept</span><span class="sxs-lookup"><span data-stu-id="74319-113">Accept</span></span>|<span data-ttu-id="74319-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="74319-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="74319-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="74319-115">Content-Type</span></span>|<span data-ttu-id="74319-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="74319-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="74319-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="74319-117">x-requestdigest</span></span>|<span data-ttu-id="74319-118">Подходящий дайджест для текущего сайта</span><span class="sxs-lookup"><span data-stu-id="74319-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="74319-119">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="74319-119">Request body</span></span>

|<span data-ttu-id="74319-120">Имя</span><span class="sxs-lookup"><span data-stu-id="74319-120">Name</span></span>    |<span data-ttu-id="74319-121">Тип</span><span class="sxs-lookup"><span data-stu-id="74319-121">Type</span></span>   |<span data-ttu-id="74319-122">Описание</span><span class="sxs-lookup"><span data-stu-id="74319-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="74319-123">_metadata</span><span class="sxs-lookup"><span data-stu-id="74319-123">_metadata</span></span>|  |<span data-ttu-id="74319-124">Настройте метаданные объекта в SPO.</span><span class="sxs-lookup"><span data-stu-id="74319-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="74319-125">Всегда используйте значение {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="74319-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="74319-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="74319-126">ContentTypeGroup</span></span>|<span data-ttu-id="74319-127">строка</span><span class="sxs-lookup"><span data-stu-id="74319-127">string</span></span>|<span data-ttu-id="74319-128">Связанная группа типов контента, относящаяся к модели.</span><span class="sxs-lookup"><span data-stu-id="74319-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="74319-129">По умолчанию используется значение "Типы интеллектуального контента документа".</span><span class="sxs-lookup"><span data-stu-id="74319-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="74319-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="74319-130">ContentTypeName</span></span>|<span data-ttu-id="74319-131">строка</span><span class="sxs-lookup"><span data-stu-id="74319-131">string</span></span>|<span data-ttu-id="74319-132">Имя связанного типа контента.</span><span class="sxs-lookup"><span data-stu-id="74319-132">The associated content type name.</span></span> <span data-ttu-id="74319-133">У созданного файла модели будет такое же имя.</span><span class="sxs-lookup"><span data-stu-id="74319-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="74319-134">Ответы</span><span class="sxs-lookup"><span data-stu-id="74319-134">Responses</span></span>

| <span data-ttu-id="74319-135">Имя</span><span class="sxs-lookup"><span data-stu-id="74319-135">Name</span></span>   | <span data-ttu-id="74319-136">Тип</span><span class="sxs-lookup"><span data-stu-id="74319-136">Type</span></span>  | <span data-ttu-id="74319-137">Описание</span><span class="sxs-lookup"><span data-stu-id="74319-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="74319-138">201 Создано</span><span class="sxs-lookup"><span data-stu-id="74319-138">201 Created</span></span>| |<span data-ttu-id="74319-139">Успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="74319-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="74319-140">Примеры</span><span class="sxs-lookup"><span data-stu-id="74319-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="74319-141">Создание новой модели осмысления документации под названием "Контракт Contoso"</span><span class="sxs-lookup"><span data-stu-id="74319-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="74319-142">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="74319-142">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a><span data-ttu-id="74319-143">Пример отклика</span><span class="sxs-lookup"><span data-stu-id="74319-143">Sample response</span></span>

<span data-ttu-id="74319-144">**Код состояния:** 201</span><span class="sxs-lookup"><span data-stu-id="74319-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="74319-145">См. также</span><span class="sxs-lookup"><span data-stu-id="74319-145">See also</span></span>

[<span data-ttu-id="74319-146">REST API модели осмысления документации Syntex</span><span class="sxs-lookup"><span data-stu-id="74319-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
