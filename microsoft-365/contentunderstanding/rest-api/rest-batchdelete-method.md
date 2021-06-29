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
# <a name="batchdelete"></a><span data-ttu-id="a40dd-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="a40dd-103">BatchDelete</span></span>

<span data-ttu-id="a40dd-104">Удаляет примененную модель осмысления документации из одной или нескольких библиотек.</span><span class="sxs-lookup"><span data-stu-id="a40dd-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="a40dd-105">Обратите внимание, что перед удалением модели необходимо удалить ее из всех библиотек (см. [пример](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="a40dd-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="a40dd-106">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="a40dd-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="a40dd-107">Параметры URI</span><span class="sxs-lookup"><span data-stu-id="a40dd-107">URI parameters</span></span>

<span data-ttu-id="a40dd-108">None;</span><span class="sxs-lookup"><span data-stu-id="a40dd-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="a40dd-109">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="a40dd-109">Request headers</span></span>

| <span data-ttu-id="a40dd-110">Заголовок</span><span class="sxs-lookup"><span data-stu-id="a40dd-110">Header</span></span> | <span data-ttu-id="a40dd-111">Значение</span><span class="sxs-lookup"><span data-stu-id="a40dd-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="a40dd-112">Accept</span><span class="sxs-lookup"><span data-stu-id="a40dd-112">Accept</span></span>|<span data-ttu-id="a40dd-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="a40dd-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="a40dd-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a40dd-114">Content-Type</span></span>|<span data-ttu-id="a40dd-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="a40dd-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="a40dd-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="a40dd-116">x-requestdigest</span></span>|<span data-ttu-id="a40dd-117">Подходящий дайджест для текущего сайта.</span><span class="sxs-lookup"><span data-stu-id="a40dd-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="a40dd-118">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="a40dd-118">Request body</span></span>

| <span data-ttu-id="a40dd-119">Имя</span><span class="sxs-lookup"><span data-stu-id="a40dd-119">Name</span></span> | <span data-ttu-id="a40dd-120">Обязательный</span><span class="sxs-lookup"><span data-stu-id="a40dd-120">Required</span></span> | <span data-ttu-id="a40dd-121">Тип</span><span class="sxs-lookup"><span data-stu-id="a40dd-121">Type</span></span> | <span data-ttu-id="a40dd-122">Описание</span><span class="sxs-lookup"><span data-stu-id="a40dd-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="a40dd-123">Publications</span><span class="sxs-lookup"><span data-stu-id="a40dd-123">Publications</span></span>|<span data-ttu-id="a40dd-124">Да</span><span class="sxs-lookup"><span data-stu-id="a40dd-124">yes</span></span>|<span data-ttu-id="a40dd-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="a40dd-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="a40dd-126">Коллекция объектов MachineLearningPublicationEntityData, каждый из которых определяет модель и целевую библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="a40dd-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="a40dd-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="a40dd-127">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="a40dd-128">Имя</span><span class="sxs-lookup"><span data-stu-id="a40dd-128">Name</span></span> | <span data-ttu-id="a40dd-129">Обязательный</span><span class="sxs-lookup"><span data-stu-id="a40dd-129">Required</span></span> | <span data-ttu-id="a40dd-130">Тип</span><span class="sxs-lookup"><span data-stu-id="a40dd-130">Type</span></span> | <span data-ttu-id="a40dd-131">Описание</span><span class="sxs-lookup"><span data-stu-id="a40dd-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="a40dd-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="a40dd-132">ModelUniqueId</span></span>|<span data-ttu-id="a40dd-133">да</span><span class="sxs-lookup"><span data-stu-id="a40dd-133">yes</span></span>|<span data-ttu-id="a40dd-134">строка</span><span class="sxs-lookup"><span data-stu-id="a40dd-134">string</span></span>|<span data-ttu-id="a40dd-135">Уникальный идентификатор файла модели.</span><span class="sxs-lookup"><span data-stu-id="a40dd-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="a40dd-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="a40dd-136">TargetSiteUrl</span></span>|<span data-ttu-id="a40dd-137">да</span><span class="sxs-lookup"><span data-stu-id="a40dd-137">yes</span></span>|<span data-ttu-id="a40dd-138">строка</span><span class="sxs-lookup"><span data-stu-id="a40dd-138">string</span></span>|<span data-ttu-id="a40dd-139">Полный URL-адрес сайта целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="a40dd-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="a40dd-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a40dd-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="a40dd-141">да</span><span class="sxs-lookup"><span data-stu-id="a40dd-141">yes</span></span>|<span data-ttu-id="a40dd-142">строка</span><span class="sxs-lookup"><span data-stu-id="a40dd-142">string</span></span>|<span data-ttu-id="a40dd-143">Относительный URL-адрес сервера для веб-сайта целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="a40dd-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="a40dd-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a40dd-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="a40dd-145">да</span><span class="sxs-lookup"><span data-stu-id="a40dd-145">yes</span></span>|<span data-ttu-id="a40dd-146">строка</span><span class="sxs-lookup"><span data-stu-id="a40dd-146">string</span></span>|<span data-ttu-id="a40dd-147">Относительный URL-адрес сервера целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="a40dd-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="a40dd-148">Отклик</span><span class="sxs-lookup"><span data-stu-id="a40dd-148">Response</span></span>

| <span data-ttu-id="a40dd-149">Имя</span><span class="sxs-lookup"><span data-stu-id="a40dd-149">Name</span></span>   | <span data-ttu-id="a40dd-150">Тип</span><span class="sxs-lookup"><span data-stu-id="a40dd-150">Type</span></span>  | <span data-ttu-id="a40dd-151">Описание</span><span class="sxs-lookup"><span data-stu-id="a40dd-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="a40dd-152">200 OK</span><span class="sxs-lookup"><span data-stu-id="a40dd-152">200 OK</span></span>||<span data-ttu-id="a40dd-153">Это настраиваемый API для поддержки удаления модели из библиотек с несколькими документами.</span><span class="sxs-lookup"><span data-stu-id="a40dd-153">This is a customized API to support removing a model from multi document libraries.</span></span> <span data-ttu-id="a40dd-154">В случае частичного успеха также может возвращаться отклик 200 OK и вызывающей стороне необходимо проверить текст отклика, чтобы понять, удалена ли модель из библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="a40dd-154">In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="a40dd-155">Текст отклика</span><span class="sxs-lookup"><span data-stu-id="a40dd-155">Response Body</span></span>
| <span data-ttu-id="a40dd-156">Имя</span><span class="sxs-lookup"><span data-stu-id="a40dd-156">Name</span></span>   | <span data-ttu-id="a40dd-157">Тип</span><span class="sxs-lookup"><span data-stu-id="a40dd-157">Type</span></span>  | <span data-ttu-id="a40dd-158">Описание</span><span class="sxs-lookup"><span data-stu-id="a40dd-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="a40dd-159">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="a40dd-159">TotalSuccesses</span></span>|<span data-ttu-id="a40dd-160">int</span><span class="sxs-lookup"><span data-stu-id="a40dd-160">int</span></span>|<span data-ttu-id="a40dd-161">Общее количество успешных удалений модели из библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="a40dd-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="a40dd-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="a40dd-162">TotalFailures</span></span>|<span data-ttu-id="a40dd-163">int</span><span class="sxs-lookup"><span data-stu-id="a40dd-163">int</span></span>|<span data-ttu-id="a40dd-164">Общее количество неудачных удалений модели из библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="a40dd-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="a40dd-165">Сведения</span><span class="sxs-lookup"><span data-stu-id="a40dd-165">Details</span></span>|<span data-ttu-id="a40dd-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="a40dd-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="a40dd-167">Коллекция объектов MachineLearningPublicationResult, каждый из которых определяет подробный результат удаления модели из библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="a40dd-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="a40dd-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="a40dd-168">MachineLearningPublicationResult</span></span>
| <span data-ttu-id="a40dd-169">Имя</span><span class="sxs-lookup"><span data-stu-id="a40dd-169">Name</span></span>   | <span data-ttu-id="a40dd-170">Тип</span><span class="sxs-lookup"><span data-stu-id="a40dd-170">Type</span></span>  | <span data-ttu-id="a40dd-171">Описание</span><span class="sxs-lookup"><span data-stu-id="a40dd-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="a40dd-172">StatusCode</span><span class="sxs-lookup"><span data-stu-id="a40dd-172">StatusCode</span></span>|<span data-ttu-id="a40dd-173">int</span><span class="sxs-lookup"><span data-stu-id="a40dd-173">int</span></span>|<span data-ttu-id="a40dd-174">Код состояния HTTP.</span><span class="sxs-lookup"><span data-stu-id="a40dd-174">The HTTP status code.</span></span>|
|<span data-ttu-id="a40dd-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="a40dd-175">ErrorMessage</span></span>|<span data-ttu-id="a40dd-176">строка</span><span class="sxs-lookup"><span data-stu-id="a40dd-176">string</span></span>|<span data-ttu-id="a40dd-177">Сообщение об ошибке, уведомляющее о проблемах при применении модели к библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="a40dd-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="a40dd-178">Publication</span><span class="sxs-lookup"><span data-stu-id="a40dd-178">Publication</span></span>|<span data-ttu-id="a40dd-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="a40dd-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="a40dd-180">Указывает сведения о модели и целевую библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="a40dd-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="a40dd-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="a40dd-181">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="a40dd-182">Имя</span><span class="sxs-lookup"><span data-stu-id="a40dd-182">Name</span></span> | <span data-ttu-id="a40dd-183">Тип</span><span class="sxs-lookup"><span data-stu-id="a40dd-183">Type</span></span> | <span data-ttu-id="a40dd-184">Описание</span><span class="sxs-lookup"><span data-stu-id="a40dd-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="a40dd-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="a40dd-185">ModelUniqueId</span></span>|<span data-ttu-id="a40dd-186">строка</span><span class="sxs-lookup"><span data-stu-id="a40dd-186">string</span></span>|<span data-ttu-id="a40dd-187">Уникальный идентификатор файла модели.</span><span class="sxs-lookup"><span data-stu-id="a40dd-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="a40dd-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="a40dd-188">TargetSiteUrl</span></span>|<span data-ttu-id="a40dd-189">строка</span><span class="sxs-lookup"><span data-stu-id="a40dd-189">string</span></span>|<span data-ttu-id="a40dd-190">Полный URL-адрес сайта целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="a40dd-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="a40dd-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a40dd-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="a40dd-192">строка</span><span class="sxs-lookup"><span data-stu-id="a40dd-192">string</span></span>|<span data-ttu-id="a40dd-193">Относительный URL-адрес сервера для веб-сайта целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="a40dd-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="a40dd-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a40dd-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="a40dd-195">строка</span><span class="sxs-lookup"><span data-stu-id="a40dd-195">string</span></span>|<span data-ttu-id="a40dd-196">Относительный URL-адрес сервера целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="a40dd-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="a40dd-197">Примеры</span><span class="sxs-lookup"><span data-stu-id="a40dd-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="a40dd-198">Удаление модели из библиотеки контрактных документов на сайте репозитория</span><span class="sxs-lookup"><span data-stu-id="a40dd-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="a40dd-199">В этом примере для модели осмысления документации контрактов Contoso используется ИД `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="a40dd-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="a40dd-200">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="a40dd-200">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="a40dd-201">Пример отклика</span><span class="sxs-lookup"><span data-stu-id="a40dd-201">Sample response</span></span>

<span data-ttu-id="a40dd-202">В отклике параметры TotalFailures и TotalSuccesses указывают на количество неудачных и успешных удалений модели из указанных библиотек.</span><span class="sxs-lookup"><span data-stu-id="a40dd-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="a40dd-203">**Код состояния:** 200</span><span class="sxs-lookup"><span data-stu-id="a40dd-203">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a40dd-204">См. также</span><span class="sxs-lookup"><span data-stu-id="a40dd-204">See also</span></span>

[<span data-ttu-id="a40dd-205">REST API модели осмысления документации Syntex</span><span class="sxs-lookup"><span data-stu-id="a40dd-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
