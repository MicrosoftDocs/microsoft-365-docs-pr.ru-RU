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
# <a name="create-model"></a><span data-ttu-id="2c9be-103">Создание модели</span><span class="sxs-lookup"><span data-stu-id="2c9be-103">Create model</span></span>

<span data-ttu-id="2c9be-104">Создает модель и связанный тип контента.</span><span class="sxs-lookup"><span data-stu-id="2c9be-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="2c9be-105">Обратите внимание, что при этом модель только создается.</span><span class="sxs-lookup"><span data-stu-id="2c9be-105">Note that this only creates the model.</span></span> <span data-ttu-id="2c9be-106">Ее по-прежнему потребуется обучить в центре контента (см. [пример](rest-createmodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="2c9be-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="2c9be-107">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="2c9be-107">HTTP request</span></span>

```http
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="2c9be-108">Параметры URI</span><span class="sxs-lookup"><span data-stu-id="2c9be-108">URI Parameters</span></span>

<span data-ttu-id="2c9be-109">None;</span><span class="sxs-lookup"><span data-stu-id="2c9be-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="2c9be-110">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="2c9be-110">Request headers</span></span>

| <span data-ttu-id="2c9be-111">Заголовок</span><span class="sxs-lookup"><span data-stu-id="2c9be-111">Header</span></span> | <span data-ttu-id="2c9be-112">Значение</span><span class="sxs-lookup"><span data-stu-id="2c9be-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="2c9be-113">Accept</span><span class="sxs-lookup"><span data-stu-id="2c9be-113">Accept</span></span>|<span data-ttu-id="2c9be-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="2c9be-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="2c9be-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="2c9be-115">Content-Type</span></span>|<span data-ttu-id="2c9be-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="2c9be-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="2c9be-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="2c9be-117">x-requestdigest</span></span>|<span data-ttu-id="2c9be-118">Подходящий дайджест для текущего сайта</span><span class="sxs-lookup"><span data-stu-id="2c9be-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="2c9be-119">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="2c9be-119">Request body</span></span>

|<span data-ttu-id="2c9be-120">Имя</span><span class="sxs-lookup"><span data-stu-id="2c9be-120">Name</span></span>    |<span data-ttu-id="2c9be-121">Тип</span><span class="sxs-lookup"><span data-stu-id="2c9be-121">Type</span></span>   |<span data-ttu-id="2c9be-122">Описание</span><span class="sxs-lookup"><span data-stu-id="2c9be-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="2c9be-123">_metadata</span><span class="sxs-lookup"><span data-stu-id="2c9be-123">_metadata</span></span>|  |<span data-ttu-id="2c9be-124">Настройте метаданные объекта в SPO.</span><span class="sxs-lookup"><span data-stu-id="2c9be-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="2c9be-125">Всегда используйте значение {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="2c9be-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="2c9be-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="2c9be-126">ContentTypeGroup</span></span>|<span data-ttu-id="2c9be-127">строка</span><span class="sxs-lookup"><span data-stu-id="2c9be-127">string</span></span>|<span data-ttu-id="2c9be-128">Связанная группа типов контента, относящаяся к модели.</span><span class="sxs-lookup"><span data-stu-id="2c9be-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="2c9be-129">По умолчанию используется значение "Типы интеллектуального контента документа".</span><span class="sxs-lookup"><span data-stu-id="2c9be-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="2c9be-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="2c9be-130">ContentTypeName</span></span>|<span data-ttu-id="2c9be-131">строка</span><span class="sxs-lookup"><span data-stu-id="2c9be-131">string</span></span>|<span data-ttu-id="2c9be-132">Имя связанного типа контента.</span><span class="sxs-lookup"><span data-stu-id="2c9be-132">The associated content type name.</span></span> <span data-ttu-id="2c9be-133">У созданного файла модели будет такое же имя.</span><span class="sxs-lookup"><span data-stu-id="2c9be-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="2c9be-134">Ответы</span><span class="sxs-lookup"><span data-stu-id="2c9be-134">Responses</span></span>

| <span data-ttu-id="2c9be-135">Имя</span><span class="sxs-lookup"><span data-stu-id="2c9be-135">Name</span></span>   | <span data-ttu-id="2c9be-136">Тип</span><span class="sxs-lookup"><span data-stu-id="2c9be-136">Type</span></span>  | <span data-ttu-id="2c9be-137">Описание</span><span class="sxs-lookup"><span data-stu-id="2c9be-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="2c9be-138">201 Создано</span><span class="sxs-lookup"><span data-stu-id="2c9be-138">201 Created</span></span>| |<span data-ttu-id="2c9be-139">Успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="2c9be-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="2c9be-140">Примеры</span><span class="sxs-lookup"><span data-stu-id="2c9be-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="2c9be-141">Создание новой модели осмысления документации под названием "Контракт Contoso"</span><span class="sxs-lookup"><span data-stu-id="2c9be-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="2c9be-142">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="2c9be-142">Sample request</span></span>

```json
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a><span data-ttu-id="2c9be-143">Пример отклика</span><span class="sxs-lookup"><span data-stu-id="2c9be-143">Sample response</span></span>

<span data-ttu-id="2c9be-144">**Код состояния:** 201</span><span class="sxs-lookup"><span data-stu-id="2c9be-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="2c9be-145">См. также</span><span class="sxs-lookup"><span data-stu-id="2c9be-145">See also</span></span>

[<span data-ttu-id="2c9be-146">REST API модели осмысления документации Syntex</span><span class="sxs-lookup"><span data-stu-id="2c9be-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
