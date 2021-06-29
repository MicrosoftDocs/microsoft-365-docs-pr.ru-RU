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
ms.openlocfilehash: 3a796bcdb38a9a6930b51f7d585febb69082732e
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177085"
---
# <a name="create-classification-request"></a><span data-ttu-id="f254e-103">Создание запроса классификации</span><span class="sxs-lookup"><span data-stu-id="f254e-103">Create classification request</span></span>

<span data-ttu-id="f254e-104">Создает запрос на классификацию одного или нескольких файлов с помощью примененной модели осмысления документации (см. [пример](rest-createclassificationrequest.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="f254e-104">Creates a request to classify one or more files using the applied document understanding model (see [example](rest-createclassificationrequest.md#examples)).</span></span>

<span data-ttu-id="f254e-105">Служба REST в SharePoint Online (а также локальной среде SharePoint 2016 или более поздней версии) поддерживает объединение нескольких запросов.</span><span class="sxs-lookup"><span data-stu-id="f254e-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests.</span></span> <span data-ttu-id="f254e-106">Запросы объединяются в один вызов службы с помощью параметра запроса $batch OData.</span><span class="sxs-lookup"><span data-stu-id="f254e-106">Requests are combined into a single call to the service by using the OData $batch query option.</span></span> <span data-ttu-id="f254e-107">Этот метод можно использовать для одновременной постановки в очередь рабочих элементов классификации для сотен документов.</span><span class="sxs-lookup"><span data-stu-id="f254e-107">This method can be used to enqueue classification work items for hundreds of documents at one time.</span></span>

## <a name="http-request"></a><span data-ttu-id="f254e-108">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="f254e-108">HTTP request</span></span>

```
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="f254e-109">Параметры URI</span><span class="sxs-lookup"><span data-stu-id="f254e-109">URI Parameters</span></span>

<span data-ttu-id="f254e-110">None;</span><span class="sxs-lookup"><span data-stu-id="f254e-110">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="f254e-111">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="f254e-111">Request headers</span></span>

| <span data-ttu-id="f254e-112">Заголовок</span><span class="sxs-lookup"><span data-stu-id="f254e-112">Header</span></span> | <span data-ttu-id="f254e-113">Значение</span><span class="sxs-lookup"><span data-stu-id="f254e-113">Value</span></span> |
|--------|-------|
|<span data-ttu-id="f254e-114">Accept</span><span class="sxs-lookup"><span data-stu-id="f254e-114">Accept</span></span>|<span data-ttu-id="f254e-115">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="f254e-115">application/json;odata=verbose</span></span>|
|<span data-ttu-id="f254e-116">Content-Type</span><span class="sxs-lookup"><span data-stu-id="f254e-116">Content-Type</span></span>|<span data-ttu-id="f254e-117">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="f254e-117">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="f254e-118">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="f254e-118">x-requestdigest</span></span>|<span data-ttu-id="f254e-119">Подходящий дайджест для текущего сайта</span><span class="sxs-lookup"><span data-stu-id="f254e-119">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="f254e-120">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="f254e-120">Request body</span></span>

|<span data-ttu-id="f254e-121">Имя</span><span class="sxs-lookup"><span data-stu-id="f254e-121">Name</span></span>    |<span data-ttu-id="f254e-122">Тип</span><span class="sxs-lookup"><span data-stu-id="f254e-122">Type</span></span>   |<span data-ttu-id="f254e-123">Описание</span><span class="sxs-lookup"><span data-stu-id="f254e-123">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="f254e-124">_metadata</span><span class="sxs-lookup"><span data-stu-id="f254e-124">_metadata</span></span>|<span data-ttu-id="f254e-125">строка</span><span class="sxs-lookup"><span data-stu-id="f254e-125">string</span></span> |<span data-ttu-id="f254e-126">Настройте метаданные объекта в SPO.</span><span class="sxs-lookup"><span data-stu-id="f254e-126">Set the object meta on the SPO.</span></span> <span data-ttu-id="f254e-127">Всегда используйте значение {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="f254e-127">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span></span> |
|<span data-ttu-id="f254e-128">TargetSiteId</span><span class="sxs-lookup"><span data-stu-id="f254e-128">TargetSiteId</span></span>|<span data-ttu-id="f254e-129">guid</span><span class="sxs-lookup"><span data-stu-id="f254e-129">guid</span></span>|<span data-ttu-id="f254e-130">ИД сайта, на котором расположен файл для классификации.</span><span class="sxs-lookup"><span data-stu-id="f254e-130">The id of the site where the file to classify is located.</span></span>|
|<span data-ttu-id="f254e-131">TargetWebId</span><span class="sxs-lookup"><span data-stu-id="f254e-131">TargetWebId</span></span>|<span data-ttu-id="f254e-132">guid</span><span class="sxs-lookup"><span data-stu-id="f254e-132">guid</span></span>|<span data-ttu-id="f254e-133">ИД веб-сайта, на котором расположен файл для классификации.</span><span class="sxs-lookup"><span data-stu-id="f254e-133">The id of the web where the file to classify is located.</span></span>|
|<span data-ttu-id="f254e-134">TargetUniqueId</span><span class="sxs-lookup"><span data-stu-id="f254e-134">TargetUniqueId</span></span>|<span data-ttu-id="f254e-135">guid</span><span class="sxs-lookup"><span data-stu-id="f254e-135">guid</span></span>|<span data-ttu-id="f254e-136">ИД файла для классификации.</span><span class="sxs-lookup"><span data-stu-id="f254e-136">The id of the file to classify.</span></span>|

## <a name="responses"></a><span data-ttu-id="f254e-137">Ответы</span><span class="sxs-lookup"><span data-stu-id="f254e-137">Responses</span></span>

| <span data-ttu-id="f254e-138">Имя</span><span class="sxs-lookup"><span data-stu-id="f254e-138">Name</span></span>   | <span data-ttu-id="f254e-139">Тип</span><span class="sxs-lookup"><span data-stu-id="f254e-139">Type</span></span>  | <span data-ttu-id="f254e-140">Описание</span><span class="sxs-lookup"><span data-stu-id="f254e-140">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="f254e-141">201 Создано</span><span class="sxs-lookup"><span data-stu-id="f254e-141">201 Created</span></span>| |<span data-ttu-id="f254e-142">Успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="f254e-142">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="f254e-143">Примеры</span><span class="sxs-lookup"><span data-stu-id="f254e-143">Examples</span></span>

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a><span data-ttu-id="f254e-144">Постановка в очередь запроса на классификацию файла с ИД "e6cff8b7-c90c-4564-b5b8-033449090932"</span><span class="sxs-lookup"><span data-stu-id="f254e-144">Enqueue a request to classify a file of id "e6cff8b7-c90c-4564-b5b8-033449090932"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="f254e-145">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="f254e-145">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a><span data-ttu-id="f254e-146">Пример отклика</span><span class="sxs-lookup"><span data-stu-id="f254e-146">Sample response</span></span>

<span data-ttu-id="f254e-147">**Код состояния:** 201</span><span class="sxs-lookup"><span data-stu-id="f254e-147">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="f254e-148">См. также</span><span class="sxs-lookup"><span data-stu-id="f254e-148">See also</span></span>

[<span data-ttu-id="f254e-149">REST API модели осмысления документации Syntex</span><span class="sxs-lookup"><span data-stu-id="f254e-149">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
