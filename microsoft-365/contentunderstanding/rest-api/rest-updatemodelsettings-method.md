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
ms.openlocfilehash: c75f669913f16233c6015230a60643cf86f33f5a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288651"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="c560f-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="c560f-103">UpdateModelSettings</span></span>

<span data-ttu-id="c560f-104">Обновляет доступные параметры моделей (связанную метку хранения и описание модели) для модели осмысления документации SharePoint Syntex (см. [пример](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="c560f-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="c560f-105">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="c560f-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="c560f-106">Параметры URI</span><span class="sxs-lookup"><span data-stu-id="c560f-106">URI parameters</span></span>

|<span data-ttu-id="c560f-107">Имя</span><span class="sxs-lookup"><span data-stu-id="c560f-107">Name</span></span> |<span data-ttu-id="c560f-108">Куда включается</span><span class="sxs-lookup"><span data-stu-id="c560f-108">In</span></span> |<span data-ttu-id="c560f-109">Обязательный</span><span class="sxs-lookup"><span data-stu-id="c560f-109">Required</span></span>|<span data-ttu-id="c560f-110">Тип</span><span class="sxs-lookup"><span data-stu-id="c560f-110">Type</span></span>|<span data-ttu-id="c560f-111">Описание</span><span class="sxs-lookup"><span data-stu-id="c560f-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="c560f-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="c560f-112">modelFileName</span></span>|<span data-ttu-id="c560f-113">Запрос</span><span class="sxs-lookup"><span data-stu-id="c560f-113">query</span></span>|<span data-ttu-id="c560f-114">True</span><span class="sxs-lookup"><span data-stu-id="c560f-114">True</span></span>|<span data-ttu-id="c560f-115">string</span><span class="sxs-lookup"><span data-stu-id="c560f-115">string</span></span>|<span data-ttu-id="c560f-116">Имя файла модели Syntex.</span><span class="sxs-lookup"><span data-stu-id="c560f-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="c560f-117">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="c560f-117">Request headers</span></span>

| <span data-ttu-id="c560f-118">Заголовок</span><span class="sxs-lookup"><span data-stu-id="c560f-118">Header</span></span> | <span data-ttu-id="c560f-119">Значение</span><span class="sxs-lookup"><span data-stu-id="c560f-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="c560f-120">Accept</span><span class="sxs-lookup"><span data-stu-id="c560f-120">Accept</span></span>|<span data-ttu-id="c560f-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="c560f-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="c560f-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c560f-122">Content-Type</span></span>|<span data-ttu-id="c560f-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="c560f-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="c560f-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="c560f-124">x-requestdigest</span></span>|<span data-ttu-id="c560f-125">Подходящий дайджест для текущего сайта.</span><span class="sxs-lookup"><span data-stu-id="c560f-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="c560f-126">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="c560f-126">Request body</span></span>

|<span data-ttu-id="c560f-127">Имя</span><span class="sxs-lookup"><span data-stu-id="c560f-127">Name</span></span>    |<span data-ttu-id="c560f-128">Тип</span><span class="sxs-lookup"><span data-stu-id="c560f-128">Type</span></span>   |<span data-ttu-id="c560f-129">Описание</span><span class="sxs-lookup"><span data-stu-id="c560f-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="c560f-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="c560f-130">ModelSettings</span></span>|<span data-ttu-id="c560f-131">строка</span><span class="sxs-lookup"><span data-stu-id="c560f-131">string</span></span>|<span data-ttu-id="c560f-132">Формат JSON параметров модели.</span><span class="sxs-lookup"><span data-stu-id="c560f-132">JSON of model settings.</span></span>|
|<span data-ttu-id="c560f-133">Описание</span><span class="sxs-lookup"><span data-stu-id="c560f-133">Description</span></span>|<span data-ttu-id="c560f-134">string</span><span class="sxs-lookup"><span data-stu-id="c560f-134">string</span></span>|<span data-ttu-id="c560f-135">Описание модели.</span><span class="sxs-lookup"><span data-stu-id="c560f-135">The model description.</span></span>|
|<span data-ttu-id="c560f-136">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="c560f-136">RetentionLabel</span></span>| |<span data-ttu-id="c560f-137">Сведения для связанной метки (ИД и имя метки).</span><span class="sxs-lookup"><span data-stu-id="c560f-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="c560f-138">Ответы</span><span class="sxs-lookup"><span data-stu-id="c560f-138">Responses</span></span>

| <span data-ttu-id="c560f-139">Имя</span><span class="sxs-lookup"><span data-stu-id="c560f-139">Name</span></span>   | <span data-ttu-id="c560f-140">Тип</span><span class="sxs-lookup"><span data-stu-id="c560f-140">Type</span></span>  | <span data-ttu-id="c560f-141">Описание</span><span class="sxs-lookup"><span data-stu-id="c560f-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="c560f-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="c560f-142">200 OK</span></span>| |<span data-ttu-id="c560f-143">Успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="c560f-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="c560f-144">Примеры</span><span class="sxs-lookup"><span data-stu-id="c560f-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="c560f-145">Обновление параметров модели для контрактов Contoso</span><span class="sxs-lookup"><span data-stu-id="c560f-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="c560f-146">В этом примере обновляется описание модели и метка хранения "Стандартное удержание".</span><span class="sxs-lookup"><span data-stu-id="c560f-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="c560f-147">ИД метки хранения: `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="c560f-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="c560f-148">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="c560f-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="c560f-149">Пример отклика</span><span class="sxs-lookup"><span data-stu-id="c560f-149">Sample response</span></span>

<span data-ttu-id="c560f-150">**Код состояния:** 200</span><span class="sxs-lookup"><span data-stu-id="c560f-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="c560f-151">См. также</span><span class="sxs-lookup"><span data-stu-id="c560f-151">See also</span></span>

[<span data-ttu-id="c560f-152">REST API модели осмысления документации Syntex</span><span class="sxs-lookup"><span data-stu-id="c560f-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
