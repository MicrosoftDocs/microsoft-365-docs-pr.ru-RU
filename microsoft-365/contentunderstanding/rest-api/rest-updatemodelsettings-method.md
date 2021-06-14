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
# <a name="updatemodelsettings"></a><span data-ttu-id="f0bfd-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="f0bfd-103">UpdateModelSettings</span></span>

<span data-ttu-id="f0bfd-104">Обновляет доступные параметры моделей (связанную метку хранения и описание модели) для модели осмысления документации SharePoint Syntex (см. [пример](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="f0bfd-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="f0bfd-105">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="f0bfd-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="f0bfd-106">Параметры URI</span><span class="sxs-lookup"><span data-stu-id="f0bfd-106">URI parameters</span></span>

<span data-ttu-id="f0bfd-107">None;</span><span class="sxs-lookup"><span data-stu-id="f0bfd-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="f0bfd-108">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="f0bfd-108">Request headers</span></span>

| <span data-ttu-id="f0bfd-109">Заголовок</span><span class="sxs-lookup"><span data-stu-id="f0bfd-109">Header</span></span> | <span data-ttu-id="f0bfd-110">Значение</span><span class="sxs-lookup"><span data-stu-id="f0bfd-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="f0bfd-111">Accept</span><span class="sxs-lookup"><span data-stu-id="f0bfd-111">Accept</span></span>|<span data-ttu-id="f0bfd-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="f0bfd-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="f0bfd-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="f0bfd-113">Content-Type</span></span>|<span data-ttu-id="f0bfd-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="f0bfd-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="f0bfd-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="f0bfd-115">x-requestdigest</span></span>|<span data-ttu-id="f0bfd-116">Подходящий дайджест для текущего сайта.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-116">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="f0bfd-117">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="f0bfd-117">Request body</span></span>

|<span data-ttu-id="f0bfd-118">Имя</span><span class="sxs-lookup"><span data-stu-id="f0bfd-118">Name</span></span>    |<span data-ttu-id="f0bfd-119">Тип</span><span class="sxs-lookup"><span data-stu-id="f0bfd-119">Type</span></span>   |<span data-ttu-id="f0bfd-120">Описание</span><span class="sxs-lookup"><span data-stu-id="f0bfd-120">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="f0bfd-121">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="f0bfd-121">ModelSettings</span></span>|<span data-ttu-id="f0bfd-122">строка</span><span class="sxs-lookup"><span data-stu-id="f0bfd-122">string</span></span>|<span data-ttu-id="f0bfd-123">Формат JSON параметров модели.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-123">JSON of model settings.</span></span>|
|<span data-ttu-id="f0bfd-124">Описание</span><span class="sxs-lookup"><span data-stu-id="f0bfd-124">Description</span></span>|<span data-ttu-id="f0bfd-125">string</span><span class="sxs-lookup"><span data-stu-id="f0bfd-125">string</span></span>|<span data-ttu-id="f0bfd-126">Описание модели.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-126">The model description.</span></span>|
|<span data-ttu-id="f0bfd-127">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="f0bfd-127">RetentionLabel</span></span>| |<span data-ttu-id="f0bfd-128">Сведения для связанной метки (ИД и имя метки).</span><span class="sxs-lookup"><span data-stu-id="f0bfd-128">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="f0bfd-129">Ответы</span><span class="sxs-lookup"><span data-stu-id="f0bfd-129">Responses</span></span>

| <span data-ttu-id="f0bfd-130">Имя</span><span class="sxs-lookup"><span data-stu-id="f0bfd-130">Name</span></span>   | <span data-ttu-id="f0bfd-131">Тип</span><span class="sxs-lookup"><span data-stu-id="f0bfd-131">Type</span></span>  | <span data-ttu-id="f0bfd-132">Описание</span><span class="sxs-lookup"><span data-stu-id="f0bfd-132">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="f0bfd-133">200 OK</span><span class="sxs-lookup"><span data-stu-id="f0bfd-133">200 OK</span></span>| |<span data-ttu-id="f0bfd-134">Успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="f0bfd-134">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="f0bfd-135">Примеры</span><span class="sxs-lookup"><span data-stu-id="f0bfd-135">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="f0bfd-136">Обновление параметров модели для контрактов Contoso</span><span class="sxs-lookup"><span data-stu-id="f0bfd-136">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="f0bfd-137">В этом примере обновляется описание модели и метка хранения "Стандартное удержание".</span><span class="sxs-lookup"><span data-stu-id="f0bfd-137">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="f0bfd-138">ИД метки хранения: `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-138">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="f0bfd-139">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="f0bfd-139">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="f0bfd-140">Пример отклика</span><span class="sxs-lookup"><span data-stu-id="f0bfd-140">Sample response</span></span>

<span data-ttu-id="f0bfd-141">**Код состояния:** 200</span><span class="sxs-lookup"><span data-stu-id="f0bfd-141">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="f0bfd-142">См. также</span><span class="sxs-lookup"><span data-stu-id="f0bfd-142">See also</span></span>

[<span data-ttu-id="f0bfd-143">REST API модели осмысления документации Syntex</span><span class="sxs-lookup"><span data-stu-id="f0bfd-143">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
