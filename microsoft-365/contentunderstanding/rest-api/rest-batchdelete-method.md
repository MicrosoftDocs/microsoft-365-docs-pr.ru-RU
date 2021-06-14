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
# <a name="batchdelete"></a><span data-ttu-id="feb98-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="feb98-103">BatchDelete</span></span>

<span data-ttu-id="feb98-104">Удаляет примененную модель осмысления документации из одной или нескольких библиотек.</span><span class="sxs-lookup"><span data-stu-id="feb98-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="feb98-105">Обратите внимание, что перед удалением модели необходимо удалить ее из всех библиотек (см. [пример](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="feb98-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="feb98-106">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="feb98-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="feb98-107">Параметры URI</span><span class="sxs-lookup"><span data-stu-id="feb98-107">URI parameters</span></span>

<span data-ttu-id="feb98-108">None;</span><span class="sxs-lookup"><span data-stu-id="feb98-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="feb98-109">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="feb98-109">Request headers</span></span>

| <span data-ttu-id="feb98-110">Заголовок</span><span class="sxs-lookup"><span data-stu-id="feb98-110">Header</span></span> | <span data-ttu-id="feb98-111">Значение</span><span class="sxs-lookup"><span data-stu-id="feb98-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="feb98-112">Accept</span><span class="sxs-lookup"><span data-stu-id="feb98-112">Accept</span></span>|<span data-ttu-id="feb98-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="feb98-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="feb98-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="feb98-114">Content-Type</span></span>|<span data-ttu-id="feb98-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="feb98-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="feb98-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="feb98-116">x-requestdigest</span></span>|<span data-ttu-id="feb98-117">Подходящий дайджест для текущего сайта.</span><span class="sxs-lookup"><span data-stu-id="feb98-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="feb98-118">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="feb98-118">Request body</span></span>

| <span data-ttu-id="feb98-119">Имя</span><span class="sxs-lookup"><span data-stu-id="feb98-119">Name</span></span> | <span data-ttu-id="feb98-120">Обязательный</span><span class="sxs-lookup"><span data-stu-id="feb98-120">Required</span></span> | <span data-ttu-id="feb98-121">Тип</span><span class="sxs-lookup"><span data-stu-id="feb98-121">Type</span></span> | <span data-ttu-id="feb98-122">Описание</span><span class="sxs-lookup"><span data-stu-id="feb98-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="feb98-123">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="feb98-123">ModelUniqueId</span></span>|<span data-ttu-id="feb98-124">да</span><span class="sxs-lookup"><span data-stu-id="feb98-124">yes</span></span>|<span data-ttu-id="feb98-125">строка</span><span class="sxs-lookup"><span data-stu-id="feb98-125">string</span></span>|<span data-ttu-id="feb98-126">Уникальный идентификатор файла модели.</span><span class="sxs-lookup"><span data-stu-id="feb98-126">The unique ID of the model file.</span></span>|
<span data-ttu-id="feb98-127">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="feb98-127">TargetSiteUrl</span></span>|<span data-ttu-id="feb98-128">да</span><span class="sxs-lookup"><span data-stu-id="feb98-128">yes</span></span>|<span data-ttu-id="feb98-129">строка</span><span class="sxs-lookup"><span data-stu-id="feb98-129">string</span></span>|<span data-ttu-id="feb98-130">Полный URL-адрес сайта целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="feb98-130">The full URL of the target library site.</span></span>|
<span data-ttu-id="feb98-131">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="feb98-131">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="feb98-132">да</span><span class="sxs-lookup"><span data-stu-id="feb98-132">yes</span></span>|<span data-ttu-id="feb98-133">строка</span><span class="sxs-lookup"><span data-stu-id="feb98-133">string</span></span>|<span data-ttu-id="feb98-134">Относительный URL-адрес сервера для веб-сайта целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="feb98-134">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="feb98-135">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="feb98-135">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="feb98-136">да</span><span class="sxs-lookup"><span data-stu-id="feb98-136">yes</span></span>|<span data-ttu-id="feb98-137">строка</span><span class="sxs-lookup"><span data-stu-id="feb98-137">string</span></span>|<span data-ttu-id="feb98-138">Относительный URL-адрес сервера целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="feb98-138">The server relative URL of the target library.</span></span>|
<span data-ttu-id="feb98-139">ViewOption</span><span class="sxs-lookup"><span data-stu-id="feb98-139">ViewOption</span></span>|<span data-ttu-id="feb98-140">Нет</span><span class="sxs-lookup"><span data-stu-id="feb98-140">no</span></span>|<span data-ttu-id="feb98-141">string</span><span class="sxs-lookup"><span data-stu-id="feb98-141">string</span></span>|<span data-ttu-id="feb98-142">Указывает, следует ли установить новое представление модели в качестве библиотеки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="feb98-142">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="feb98-143">Отклик</span><span class="sxs-lookup"><span data-stu-id="feb98-143">Response</span></span>

| <span data-ttu-id="feb98-144">Имя</span><span class="sxs-lookup"><span data-stu-id="feb98-144">Name</span></span>   | <span data-ttu-id="feb98-145">Тип</span><span class="sxs-lookup"><span data-stu-id="feb98-145">Type</span></span>  | <span data-ttu-id="feb98-146">Описание</span><span class="sxs-lookup"><span data-stu-id="feb98-146">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="feb98-147">200 OK</span><span class="sxs-lookup"><span data-stu-id="feb98-147">200 OK</span></span>| |<span data-ttu-id="feb98-148">Успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="feb98-148">Success</span></span>|


## <a name="examples"></a><span data-ttu-id="feb98-149">Примеры</span><span class="sxs-lookup"><span data-stu-id="feb98-149">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="feb98-150">Удаление модели из библиотеки контрактных документов на сайте репозитория</span><span class="sxs-lookup"><span data-stu-id="feb98-150">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="feb98-151">В этом примере для модели осмысления документации контрактов Contoso используется ИД `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="feb98-151">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="feb98-152">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="feb98-152">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="feb98-153">Пример отклика</span><span class="sxs-lookup"><span data-stu-id="feb98-153">Sample response</span></span>

<span data-ttu-id="feb98-154">В отклике параметры TotalFailures и TotalSuccesses указывают на количество сбоев и успешных выполнений модели, применяемой к указанным библиотекам.</span><span class="sxs-lookup"><span data-stu-id="feb98-154">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="feb98-155">**Код состояния:** 200</span><span class="sxs-lookup"><span data-stu-id="feb98-155">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="feb98-156">См. также</span><span class="sxs-lookup"><span data-stu-id="feb98-156">See also</span></span>

[<span data-ttu-id="feb98-157">REST API модели осмысления документации Syntex</span><span class="sxs-lookup"><span data-stu-id="feb98-157">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
