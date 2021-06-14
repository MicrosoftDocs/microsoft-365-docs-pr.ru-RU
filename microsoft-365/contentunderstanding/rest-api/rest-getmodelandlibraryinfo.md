---
title: Получение сведений о модели и библиотеке
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
description: Используйте REST API для получения сведений о модели и библиотеке, к которой она была применена.
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904300"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="10ebb-103">Получение сведений о модели и библиотеке</span><span class="sxs-lookup"><span data-stu-id="10ebb-103">Get model and library information</span></span>

<span data-ttu-id="10ebb-104">Получение сведений о модели и библиотеке, к которой она была применена (см. [пример](rest-getmodelandlibraryinfo.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="10ebb-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="10ebb-105">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="10ebb-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="10ebb-106">Параметры URI</span><span class="sxs-lookup"><span data-stu-id="10ebb-106">URI parameters</span></span>

| <span data-ttu-id="10ebb-107">Имя</span><span class="sxs-lookup"><span data-stu-id="10ebb-107">Name</span></span> | <span data-ttu-id="10ebb-108">Куда включается</span><span class="sxs-lookup"><span data-stu-id="10ebb-108">In</span></span> | <span data-ttu-id="10ebb-109">Обязательный</span><span class="sxs-lookup"><span data-stu-id="10ebb-109">Required</span></span> | <span data-ttu-id="10ebb-110">Тип</span><span class="sxs-lookup"><span data-stu-id="10ebb-110">Type</span></span> | <span data-ttu-id="10ebb-111">Описание</span><span class="sxs-lookup"><span data-stu-id="10ebb-111">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="10ebb-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="10ebb-112">ModelUniqueId</span></span>|<span data-ttu-id="10ebb-113">Запрос</span><span class="sxs-lookup"><span data-stu-id="10ebb-113">query</span></span>|<span data-ttu-id="10ebb-114">True</span><span class="sxs-lookup"><span data-stu-id="10ebb-114">True</span></span>|<span data-ttu-id="10ebb-115">GUID</span><span class="sxs-lookup"><span data-stu-id="10ebb-115">GUID</span></span>|<span data-ttu-id="10ebb-116">Уникальный идентификатор файла модели.</span><span class="sxs-lookup"><span data-stu-id="10ebb-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="10ebb-117">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="10ebb-117">Request headers</span></span>

| <span data-ttu-id="10ebb-118">Заголовок</span><span class="sxs-lookup"><span data-stu-id="10ebb-118">Header</span></span> | <span data-ttu-id="10ebb-119">Значение</span><span class="sxs-lookup"><span data-stu-id="10ebb-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="10ebb-120">Accept</span><span class="sxs-lookup"><span data-stu-id="10ebb-120">Accept</span></span>|<span data-ttu-id="10ebb-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="10ebb-121">application/json;odata=verbose</span></span>|


## <a name="request-body"></a><span data-ttu-id="10ebb-122">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="10ebb-122">Request body</span></span>

| <span data-ttu-id="10ebb-123">Имя</span><span class="sxs-lookup"><span data-stu-id="10ebb-123">Name</span></span> | <span data-ttu-id="10ebb-124">Обязательный</span><span class="sxs-lookup"><span data-stu-id="10ebb-124">Required</span></span> | <span data-ttu-id="10ebb-125">Тип</span><span class="sxs-lookup"><span data-stu-id="10ebb-125">Type</span></span> | <span data-ttu-id="10ebb-126">Описание</span><span class="sxs-lookup"><span data-stu-id="10ebb-126">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="10ebb-127">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="10ebb-127">ModelUniqueId</span></span>|<span data-ttu-id="10ebb-128">да</span><span class="sxs-lookup"><span data-stu-id="10ebb-128">yes</span></span>|<span data-ttu-id="10ebb-129">строка</span><span class="sxs-lookup"><span data-stu-id="10ebb-129">string</span></span>|<span data-ttu-id="10ebb-130">Уникальный идентификатор файла модели.</span><span class="sxs-lookup"><span data-stu-id="10ebb-130">The unique ID of the model file.</span></span>|
|<span data-ttu-id="10ebb-131">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="10ebb-131">TargetSiteUrl</span></span>|<span data-ttu-id="10ebb-132">да</span><span class="sxs-lookup"><span data-stu-id="10ebb-132">yes</span></span>|<span data-ttu-id="10ebb-133">строка</span><span class="sxs-lookup"><span data-stu-id="10ebb-133">string</span></span>|<span data-ttu-id="10ebb-134">Полный URL-адрес сайта целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="10ebb-134">The full URL of the target library site.</span></span>|
|<span data-ttu-id="10ebb-135">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="10ebb-135">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="10ebb-136">да</span><span class="sxs-lookup"><span data-stu-id="10ebb-136">yes</span></span>|<span data-ttu-id="10ebb-137">строка</span><span class="sxs-lookup"><span data-stu-id="10ebb-137">string</span></span>|<span data-ttu-id="10ebb-138">Относительный URL-адрес сервера для веб-сайта целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="10ebb-138">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="10ebb-139">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="10ebb-139">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="10ebb-140">да</span><span class="sxs-lookup"><span data-stu-id="10ebb-140">yes</span></span>|<span data-ttu-id="10ebb-141">строка</span><span class="sxs-lookup"><span data-stu-id="10ebb-141">string</span></span>|<span data-ttu-id="10ebb-142">Относительный URL-адрес сервера целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="10ebb-142">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="10ebb-143">TargetLibraryRemoved</span><span class="sxs-lookup"><span data-stu-id="10ebb-143">TargetLibraryRemoved</span></span>|<span data-ttu-id="10ebb-144">да</span><span class="sxs-lookup"><span data-stu-id="10ebb-144">yes</span></span>|<span data-ttu-id="10ebb-145">int</span><span class="sxs-lookup"><span data-stu-id="10ebb-145">int</span></span>|<span data-ttu-id="10ebb-146">Флажок, который указывает, была ли удалена целевая библиотека.</span><span class="sxs-lookup"><span data-stu-id="10ebb-146">The flag that indicates if the target library has been removed or not.</span></span>|

## <a name="response"></a><span data-ttu-id="10ebb-147">Отклик</span><span class="sxs-lookup"><span data-stu-id="10ebb-147">Response</span></span>

| <span data-ttu-id="10ebb-148">Имя</span><span class="sxs-lookup"><span data-stu-id="10ebb-148">Name</span></span>   | <span data-ttu-id="10ebb-149">Тип</span><span class="sxs-lookup"><span data-stu-id="10ebb-149">Type</span></span>  | <span data-ttu-id="10ebb-150">Описание</span><span class="sxs-lookup"><span data-stu-id="10ebb-150">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="10ebb-151">200 OK</span><span class="sxs-lookup"><span data-stu-id="10ebb-151">200 OK</span></span>| |<span data-ttu-id="10ebb-152">Успешно</span><span class="sxs-lookup"><span data-stu-id="10ebb-152">Success</span></span>|
|<span data-ttu-id="10ebb-153">201 Создано</span><span class="sxs-lookup"><span data-stu-id="10ebb-153">201 Created</span></span>| |<span data-ttu-id="10ebb-154">Обратите внимание, что поскольку этот API поддерживает применение модели к нескольким библиотекам, отклик 201 может возвращаться даже в случае сбоя при применении модели к одной из библиотек.</span><span class="sxs-lookup"><span data-stu-id="10ebb-154">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="10ebb-155">Проверьте текст отклика, чтобы понять, была ли модель успешно применена ко всем указанным библиотекам.</span><span class="sxs-lookup"><span data-stu-id="10ebb-155">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="10ebb-156">Подробности см. в разделе [Текст запроса](rest-getmodelandlibraryinfo.md#request-body).</span><span class="sxs-lookup"><span data-stu-id="10ebb-156">See [Request body](rest-getmodelandlibraryinfo.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="10ebb-157">Примеры</span><span class="sxs-lookup"><span data-stu-id="10ebb-157">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="10ebb-158">Получение сведений о модели контрактов и библиотеке документов на сайте репозитория</span><span class="sxs-lookup"><span data-stu-id="10ebb-158">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="10ebb-159">В этом примере для модели осмысления документации контрактов Contoso используется ИД `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="10ebb-159">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="10ebb-160">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="10ebb-160">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a><span data-ttu-id="10ebb-161">Пример отклика</span><span class="sxs-lookup"><span data-stu-id="10ebb-161">Sample response</span></span>

<span data-ttu-id="10ebb-162">**Код состояния:** 200</span><span class="sxs-lookup"><span data-stu-id="10ebb-162">**Status code:** 200</span></span>

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a><span data-ttu-id="10ebb-163">См. также</span><span class="sxs-lookup"><span data-stu-id="10ebb-163">See also</span></span>

[<span data-ttu-id="10ebb-164">REST API модели осмысления документации Syntex</span><span class="sxs-lookup"><span data-stu-id="10ebb-164">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
