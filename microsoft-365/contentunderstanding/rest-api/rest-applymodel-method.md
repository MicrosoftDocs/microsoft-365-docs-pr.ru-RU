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
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286541"
---
# <a name="batch-apply-model"></a><span data-ttu-id="89ec7-103">Пакетное применение модели</span><span class="sxs-lookup"><span data-stu-id="89ec7-103">Batch Apply model</span></span>

<span data-ttu-id="89ec7-104">Применяет (или синхронизирует) обученную модель осмысления документации к одной или нескольким библиотекам (см. [пример](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="89ec7-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="89ec7-105">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="89ec7-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="89ec7-106">Параметры URI</span><span class="sxs-lookup"><span data-stu-id="89ec7-106">URI parameters</span></span>

<span data-ttu-id="89ec7-107">None;</span><span class="sxs-lookup"><span data-stu-id="89ec7-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="89ec7-108">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="89ec7-108">Request headers</span></span>

| <span data-ttu-id="89ec7-109">Заголовок</span><span class="sxs-lookup"><span data-stu-id="89ec7-109">Header</span></span> | <span data-ttu-id="89ec7-110">Значение</span><span class="sxs-lookup"><span data-stu-id="89ec7-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="89ec7-111">Accept</span><span class="sxs-lookup"><span data-stu-id="89ec7-111">Accept</span></span>|<span data-ttu-id="89ec7-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="89ec7-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="89ec7-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="89ec7-113">Content-Type</span></span>|<span data-ttu-id="89ec7-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="89ec7-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="89ec7-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="89ec7-115">x-requestdigest</span></span>|<span data-ttu-id="89ec7-116">Подходящий дайджест для текущего сайта.</span><span class="sxs-lookup"><span data-stu-id="89ec7-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="89ec7-117">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="89ec7-117">Request body</span></span>

| <span data-ttu-id="89ec7-118">Имя</span><span class="sxs-lookup"><span data-stu-id="89ec7-118">Name</span></span> | <span data-ttu-id="89ec7-119">Обязательный</span><span class="sxs-lookup"><span data-stu-id="89ec7-119">Required</span></span> | <span data-ttu-id="89ec7-120">Тип</span><span class="sxs-lookup"><span data-stu-id="89ec7-120">Type</span></span> | <span data-ttu-id="89ec7-121">Описание</span><span class="sxs-lookup"><span data-stu-id="89ec7-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="89ec7-122">__metadata</span><span class="sxs-lookup"><span data-stu-id="89ec7-122">__metadata</span></span>|<span data-ttu-id="89ec7-123">да</span><span class="sxs-lookup"><span data-stu-id="89ec7-123">yes</span></span>|<span data-ttu-id="89ec7-124">строка</span><span class="sxs-lookup"><span data-stu-id="89ec7-124">string</span></span>|<span data-ttu-id="89ec7-125">Настройте метаданные объекта в SPO.</span><span class="sxs-lookup"><span data-stu-id="89ec7-125">Set the object meta on the SPO.</span></span> <span data-ttu-id="89ec7-126">Всегда используйте значение {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="89ec7-126">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span></span>|
|<span data-ttu-id="89ec7-127">Publications</span><span class="sxs-lookup"><span data-stu-id="89ec7-127">Publications</span></span>|<span data-ttu-id="89ec7-128">Да</span><span class="sxs-lookup"><span data-stu-id="89ec7-128">yes</span></span>|<span data-ttu-id="89ec7-129">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="89ec7-129">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="89ec7-130">Коллекция объектов MachineLearningPublicationEntityData, каждый из которых определяет модель и целевую библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="89ec7-130">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="89ec7-131">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="89ec7-131">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="89ec7-132">Имя</span><span class="sxs-lookup"><span data-stu-id="89ec7-132">Name</span></span> | <span data-ttu-id="89ec7-133">Обязательный</span><span class="sxs-lookup"><span data-stu-id="89ec7-133">Required</span></span> | <span data-ttu-id="89ec7-134">Тип</span><span class="sxs-lookup"><span data-stu-id="89ec7-134">Type</span></span> | <span data-ttu-id="89ec7-135">Описание</span><span class="sxs-lookup"><span data-stu-id="89ec7-135">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="89ec7-136">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="89ec7-136">ModelUniqueId</span></span>|<span data-ttu-id="89ec7-137">да</span><span class="sxs-lookup"><span data-stu-id="89ec7-137">yes</span></span>|<span data-ttu-id="89ec7-138">строка</span><span class="sxs-lookup"><span data-stu-id="89ec7-138">string</span></span>|<span data-ttu-id="89ec7-139">Уникальный идентификатор файла модели.</span><span class="sxs-lookup"><span data-stu-id="89ec7-139">The unique ID of the model file.</span></span>|
|<span data-ttu-id="89ec7-140">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="89ec7-140">TargetSiteUrl</span></span>|<span data-ttu-id="89ec7-141">да</span><span class="sxs-lookup"><span data-stu-id="89ec7-141">yes</span></span>|<span data-ttu-id="89ec7-142">строка</span><span class="sxs-lookup"><span data-stu-id="89ec7-142">string</span></span>|<span data-ttu-id="89ec7-143">Полный URL-адрес сайта целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="89ec7-143">The full URL of the target library site.</span></span>|
|<span data-ttu-id="89ec7-144">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="89ec7-144">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="89ec7-145">да</span><span class="sxs-lookup"><span data-stu-id="89ec7-145">yes</span></span>|<span data-ttu-id="89ec7-146">строка</span><span class="sxs-lookup"><span data-stu-id="89ec7-146">string</span></span>|<span data-ttu-id="89ec7-147">Относительный URL-адрес сервера для веб-сайта целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="89ec7-147">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="89ec7-148">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="89ec7-148">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="89ec7-149">да</span><span class="sxs-lookup"><span data-stu-id="89ec7-149">yes</span></span>|<span data-ttu-id="89ec7-150">строка</span><span class="sxs-lookup"><span data-stu-id="89ec7-150">string</span></span>|<span data-ttu-id="89ec7-151">Относительный URL-адрес сервера целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="89ec7-151">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="89ec7-152">ViewOption</span><span class="sxs-lookup"><span data-stu-id="89ec7-152">ViewOption</span></span>|<span data-ttu-id="89ec7-153">Нет</span><span class="sxs-lookup"><span data-stu-id="89ec7-153">no</span></span>|<span data-ttu-id="89ec7-154">string</span><span class="sxs-lookup"><span data-stu-id="89ec7-154">string</span></span>|<span data-ttu-id="89ec7-155">Указывает, следует ли установить новое представление модели в качестве библиотеки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="89ec7-155">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="89ec7-156">Отклик</span><span class="sxs-lookup"><span data-stu-id="89ec7-156">Response</span></span>

| <span data-ttu-id="89ec7-157">Имя</span><span class="sxs-lookup"><span data-stu-id="89ec7-157">Name</span></span>   | <span data-ttu-id="89ec7-158">Тип</span><span class="sxs-lookup"><span data-stu-id="89ec7-158">Type</span></span>  | <span data-ttu-id="89ec7-159">Описание</span><span class="sxs-lookup"><span data-stu-id="89ec7-159">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="89ec7-160">201 Создано</span><span class="sxs-lookup"><span data-stu-id="89ec7-160">201 Created</span></span>||<span data-ttu-id="89ec7-p102">Это настраиваемый API для поддержки применения модели к библиотекам с несколькими документами. В случае частичного успеха также может возвращаться отклик "201 создано" и вызывающей стороне необходимо проверить текст отклика, чтобы понять, применена ли модель к библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="89ec7-p102">This is a customized API to support applying a model to multi document libraries. In the case of partial success, 201 created could still be returned and the caller needs to inspect the response body to understand if the model has been successfully applied to a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="89ec7-163">Текст отклика</span><span class="sxs-lookup"><span data-stu-id="89ec7-163">Response Body</span></span>

| <span data-ttu-id="89ec7-164">Имя</span><span class="sxs-lookup"><span data-stu-id="89ec7-164">Name</span></span>   | <span data-ttu-id="89ec7-165">Тип</span><span class="sxs-lookup"><span data-stu-id="89ec7-165">Type</span></span>  | <span data-ttu-id="89ec7-166">Описание</span><span class="sxs-lookup"><span data-stu-id="89ec7-166">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="89ec7-167">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="89ec7-167">TotalSuccesses</span></span>|<span data-ttu-id="89ec7-168">int</span><span class="sxs-lookup"><span data-stu-id="89ec7-168">int</span></span>|<span data-ttu-id="89ec7-169">Общее количество успешных применений модели к библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="89ec7-169">The total number of a model being successfully applied to a document library.</span></span>|
|<span data-ttu-id="89ec7-170">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="89ec7-170">TotalFailures</span></span>|<span data-ttu-id="89ec7-171">int</span><span class="sxs-lookup"><span data-stu-id="89ec7-171">int</span></span>|<span data-ttu-id="89ec7-172">Общее количество неудачных применений модели к библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="89ec7-172">The total number of a model failing to be applied to a document library.</span></span>|
|<span data-ttu-id="89ec7-173">Сведения</span><span class="sxs-lookup"><span data-stu-id="89ec7-173">Details</span></span>|<span data-ttu-id="89ec7-174">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="89ec7-174">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="89ec7-175">Коллекция объектов MachineLearningPublicationResult, каждый из которых определяет подробный результат применения модели к библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="89ec7-175">The collection of MachineLearningPublicationResult each of which specifies the detailed result of applying the model to the document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="89ec7-176">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="89ec7-176">MachineLearningPublicationResult</span></span>

| <span data-ttu-id="89ec7-177">Имя</span><span class="sxs-lookup"><span data-stu-id="89ec7-177">Name</span></span>   | <span data-ttu-id="89ec7-178">Тип</span><span class="sxs-lookup"><span data-stu-id="89ec7-178">Type</span></span>  | <span data-ttu-id="89ec7-179">Описание</span><span class="sxs-lookup"><span data-stu-id="89ec7-179">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="89ec7-180">StatusCode</span><span class="sxs-lookup"><span data-stu-id="89ec7-180">StatusCode</span></span>|<span data-ttu-id="89ec7-181">int</span><span class="sxs-lookup"><span data-stu-id="89ec7-181">int</span></span>|<span data-ttu-id="89ec7-182">Код состояния HTTP.</span><span class="sxs-lookup"><span data-stu-id="89ec7-182">The HTTP status code.</span></span>|
|<span data-ttu-id="89ec7-183">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="89ec7-183">ErrorMessage</span></span>|<span data-ttu-id="89ec7-184">строка</span><span class="sxs-lookup"><span data-stu-id="89ec7-184">string</span></span>|<span data-ttu-id="89ec7-185">Сообщение об ошибке, уведомляющее о проблемах при применении модели к библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="89ec7-185">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="89ec7-186">Publication</span><span class="sxs-lookup"><span data-stu-id="89ec7-186">Publication</span></span>|<span data-ttu-id="89ec7-187">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="89ec7-187">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="89ec7-188">Указывает сведения о модели и целевую библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="89ec7-188">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="89ec7-189">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="89ec7-189">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="89ec7-190">Имя</span><span class="sxs-lookup"><span data-stu-id="89ec7-190">Name</span></span> | <span data-ttu-id="89ec7-191">Тип</span><span class="sxs-lookup"><span data-stu-id="89ec7-191">Type</span></span> | <span data-ttu-id="89ec7-192">Описание</span><span class="sxs-lookup"><span data-stu-id="89ec7-192">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="89ec7-193">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="89ec7-193">ModelUniqueId</span></span>|<span data-ttu-id="89ec7-194">строка</span><span class="sxs-lookup"><span data-stu-id="89ec7-194">string</span></span>|<span data-ttu-id="89ec7-195">Уникальный идентификатор файла модели.</span><span class="sxs-lookup"><span data-stu-id="89ec7-195">The unique ID of the model file.</span></span>|
|<span data-ttu-id="89ec7-196">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="89ec7-196">TargetSiteUrl</span></span>|<span data-ttu-id="89ec7-197">строка</span><span class="sxs-lookup"><span data-stu-id="89ec7-197">string</span></span>|<span data-ttu-id="89ec7-198">Полный URL-адрес сайта целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="89ec7-198">The full URL of the target library site.</span></span>|
|<span data-ttu-id="89ec7-199">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="89ec7-199">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="89ec7-200">строка</span><span class="sxs-lookup"><span data-stu-id="89ec7-200">string</span></span>|<span data-ttu-id="89ec7-201">Относительный URL-адрес сервера для веб-сайта целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="89ec7-201">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="89ec7-202">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="89ec7-202">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="89ec7-203">строка</span><span class="sxs-lookup"><span data-stu-id="89ec7-203">string</span></span>|<span data-ttu-id="89ec7-204">Относительный URL-адрес сервера целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="89ec7-204">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="89ec7-205">Примеры</span><span class="sxs-lookup"><span data-stu-id="89ec7-205">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="89ec7-206">Применение модели к библиотеке контрактных документов на сайте репозитория</span><span class="sxs-lookup"><span data-stu-id="89ec7-206">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="89ec7-207">В этом примере для модели осмысления документации контрактов Contoso используется ИД `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="89ec7-207">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="89ec7-208">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="89ec7-208">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="89ec7-209">Пример отклика</span><span class="sxs-lookup"><span data-stu-id="89ec7-209">Sample response</span></span>

<span data-ttu-id="89ec7-210">В отклике параметры TotalFailures и TotalSuccesses указывают на количество сбоев и успешных выполнений модели, применяемой к указанным библиотекам.</span><span class="sxs-lookup"><span data-stu-id="89ec7-210">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="89ec7-211">**Код состояния:** 201</span><span class="sxs-lookup"><span data-stu-id="89ec7-211">**Status code:** 201</span></span>

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

## <a name="see-also"></a><span data-ttu-id="89ec7-212">См. также</span><span class="sxs-lookup"><span data-stu-id="89ec7-212">See also</span></span>

[<span data-ttu-id="89ec7-213">REST API модели осмысления документации Syntex</span><span class="sxs-lookup"><span data-stu-id="89ec7-213">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
