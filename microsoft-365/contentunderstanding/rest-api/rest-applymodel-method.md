---
title: Применение модели
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
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904355"
---
# <a name="apply-model"></a><span data-ttu-id="902ba-103">Применение модели</span><span class="sxs-lookup"><span data-stu-id="902ba-103">Apply model</span></span>

<span data-ttu-id="902ba-104">Применяет (или синхронизирует) обученную модель осмысления документации к одной или нескольким библиотекам (см. [пример](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="902ba-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="902ba-105">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="902ba-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="902ba-106">Параметры URI</span><span class="sxs-lookup"><span data-stu-id="902ba-106">URI parameters</span></span>

<span data-ttu-id="902ba-107">None;</span><span class="sxs-lookup"><span data-stu-id="902ba-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="902ba-108">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="902ba-108">Request headers</span></span>

| <span data-ttu-id="902ba-109">Заголовок</span><span class="sxs-lookup"><span data-stu-id="902ba-109">Header</span></span> | <span data-ttu-id="902ba-110">Значение</span><span class="sxs-lookup"><span data-stu-id="902ba-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="902ba-111">Accept</span><span class="sxs-lookup"><span data-stu-id="902ba-111">Accept</span></span>|<span data-ttu-id="902ba-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="902ba-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="902ba-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="902ba-113">Content-Type</span></span>|<span data-ttu-id="902ba-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="902ba-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="902ba-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="902ba-115">x-requestdigest</span></span>|<span data-ttu-id="902ba-116">Подходящий дайджест для текущего сайта.</span><span class="sxs-lookup"><span data-stu-id="902ba-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="902ba-117">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="902ba-117">Request body</span></span>

| <span data-ttu-id="902ba-118">Имя</span><span class="sxs-lookup"><span data-stu-id="902ba-118">Name</span></span> | <span data-ttu-id="902ba-119">Обязательный</span><span class="sxs-lookup"><span data-stu-id="902ba-119">Required</span></span> | <span data-ttu-id="902ba-120">Тип</span><span class="sxs-lookup"><span data-stu-id="902ba-120">Type</span></span> | <span data-ttu-id="902ba-121">Описание</span><span class="sxs-lookup"><span data-stu-id="902ba-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="902ba-122">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="902ba-122">ModelUniqueId</span></span>|<span data-ttu-id="902ba-123">да</span><span class="sxs-lookup"><span data-stu-id="902ba-123">yes</span></span>|<span data-ttu-id="902ba-124">строка</span><span class="sxs-lookup"><span data-stu-id="902ba-124">string</span></span>|<span data-ttu-id="902ba-125">Уникальный идентификатор файла модели.</span><span class="sxs-lookup"><span data-stu-id="902ba-125">The unique ID of the model file.</span></span>|
<span data-ttu-id="902ba-126">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="902ba-126">TargetSiteUrl</span></span>|<span data-ttu-id="902ba-127">да</span><span class="sxs-lookup"><span data-stu-id="902ba-127">yes</span></span>|<span data-ttu-id="902ba-128">строка</span><span class="sxs-lookup"><span data-stu-id="902ba-128">string</span></span>|<span data-ttu-id="902ba-129">Полный URL-адрес сайта целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="902ba-129">The full URL of the target library site.</span></span>|
<span data-ttu-id="902ba-130">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="902ba-130">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="902ba-131">да</span><span class="sxs-lookup"><span data-stu-id="902ba-131">yes</span></span>|<span data-ttu-id="902ba-132">строка</span><span class="sxs-lookup"><span data-stu-id="902ba-132">string</span></span>|<span data-ttu-id="902ba-133">Относительный URL-адрес сервера для веб-сайта целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="902ba-133">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="902ba-134">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="902ba-134">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="902ba-135">да</span><span class="sxs-lookup"><span data-stu-id="902ba-135">yes</span></span>|<span data-ttu-id="902ba-136">строка</span><span class="sxs-lookup"><span data-stu-id="902ba-136">string</span></span>|<span data-ttu-id="902ba-137">Относительный URL-адрес сервера целевой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="902ba-137">The server relative URL of the target library.</span></span>|
<span data-ttu-id="902ba-138">ViewOption</span><span class="sxs-lookup"><span data-stu-id="902ba-138">ViewOption</span></span>|<span data-ttu-id="902ba-139">Нет</span><span class="sxs-lookup"><span data-stu-id="902ba-139">no</span></span>|<span data-ttu-id="902ba-140">string</span><span class="sxs-lookup"><span data-stu-id="902ba-140">string</span></span>|<span data-ttu-id="902ba-141">Указывает, следует ли установить новое представление модели в качестве библиотеки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="902ba-141">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="902ba-142">Отклик</span><span class="sxs-lookup"><span data-stu-id="902ba-142">Response</span></span>

| <span data-ttu-id="902ba-143">Имя</span><span class="sxs-lookup"><span data-stu-id="902ba-143">Name</span></span>   | <span data-ttu-id="902ba-144">Тип</span><span class="sxs-lookup"><span data-stu-id="902ba-144">Type</span></span>  | <span data-ttu-id="902ba-145">Описание</span><span class="sxs-lookup"><span data-stu-id="902ba-145">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="902ba-146">200 OK</span><span class="sxs-lookup"><span data-stu-id="902ba-146">200 OK</span></span>| |<span data-ttu-id="902ba-147">Успешно</span><span class="sxs-lookup"><span data-stu-id="902ba-147">Success</span></span>|
|<span data-ttu-id="902ba-148">201 Создано</span><span class="sxs-lookup"><span data-stu-id="902ba-148">201 Created</span></span>| |<span data-ttu-id="902ba-149">Обратите внимание, что поскольку этот API поддерживает применение модели к нескольким библиотекам, отклик 201 может возвращаться даже в случае сбоя при применении модели к одной из библиотек.</span><span class="sxs-lookup"><span data-stu-id="902ba-149">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="902ba-150">Проверьте текст отклика, чтобы понять, была ли модель успешно применена ко всем указанным библиотекам.</span><span class="sxs-lookup"><span data-stu-id="902ba-150">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="902ba-151">Подробности см. в разделе [Текст запроса](rest-applymodel-method.md#request-body).</span><span class="sxs-lookup"><span data-stu-id="902ba-151">See [Request body](rest-applymodel-method.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="902ba-152">Примеры</span><span class="sxs-lookup"><span data-stu-id="902ba-152">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="902ba-153">Применение модели к библиотеке контрактных документов на сайте репозитория</span><span class="sxs-lookup"><span data-stu-id="902ba-153">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="902ba-154">В этом примере для модели осмысления документации контрактов Contoso используется ИД `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="902ba-154">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="902ba-155">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="902ba-155">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="902ba-156">Пример отклика</span><span class="sxs-lookup"><span data-stu-id="902ba-156">Sample response</span></span>

<span data-ttu-id="902ba-157">В отклике параметры TotalFailures и TotalSuccesses указывают на количество сбоев и успешных выполнений модели, применяемой к указанным библиотекам.</span><span class="sxs-lookup"><span data-stu-id="902ba-157">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="902ba-158">**Код состояния:** 200</span><span class="sxs-lookup"><span data-stu-id="902ba-158">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="902ba-159">См. также</span><span class="sxs-lookup"><span data-stu-id="902ba-159">See also</span></span>

[<span data-ttu-id="902ba-160">REST API модели осмысления документа Syntex</span><span class="sxs-lookup"><span data-stu-id="902ba-160">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
