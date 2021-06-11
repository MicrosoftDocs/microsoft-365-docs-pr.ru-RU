---
title: Отмена API действий машины
description: Узнайте, как отменить действие уже запущенной машины
keywords: apis, graph api,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879800"
---
#   <a name="cancel-machine-action-api"></a><span data-ttu-id="d919a-104">Отмена API действий машины</span><span class="sxs-lookup"><span data-stu-id="d919a-104">Cancel machine action API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d919a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d919a-105">**Applies to:**</span></span>
- [<span data-ttu-id="d919a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d919a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="d919a-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d919a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d919a-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d919a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="d919a-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="d919a-109">API description</span></span>

<span data-ttu-id="d919a-110">Отмена уже запущенного действия машины, которое еще не в окончательном состоянии (завершено, отменено, не выполнено).</span><span class="sxs-lookup"><span data-stu-id="d919a-110">Cancel an already launched machine action that are not yet in final state (completed, cancelled, failed).</span></span>

## <a name="limitations"></a><span data-ttu-id="d919a-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d919a-111">Limitations</span></span>

1.  <span data-ttu-id="d919a-112">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="d919a-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="d919a-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="d919a-113">Permissions</span></span>

<span data-ttu-id="d919a-114">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="d919a-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d919a-115">Подробнее, в том числе о выборе разрешений, см. в [руб. Начало работы.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d919a-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

|     <span data-ttu-id="d919a-116">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="d919a-116">Permission    type</span></span>     |     <span data-ttu-id="d919a-117">Разрешение</span><span class="sxs-lookup"><span data-stu-id="d919a-117">Permission</span></span>     |    <span data-ttu-id="d919a-118">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="d919a-118">Permission    display name</span></span>     |
|-|-|-|
|    <br><span data-ttu-id="d919a-119">Приложение</span><span class="sxs-lookup"><span data-stu-id="d919a-119">Application</span></span>    |    <br><span data-ttu-id="d919a-120">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="d919a-120">Machine.CollectForensic</span></span><br>   <span data-ttu-id="d919a-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="d919a-121">Machine.Isolate</span></span>   <br><span data-ttu-id="d919a-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="d919a-122">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="d919a-123">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="d919a-123">Machine.Scan</span></span><br>   <span data-ttu-id="d919a-124">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="d919a-124">Machine.Offboard</span></span><br>   <span data-ttu-id="d919a-125">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="d919a-125">Machine.StopAndQuarantine</span></span><br>   <span data-ttu-id="d919a-126">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="d919a-126">Machine.LiveResponse</span></span>    |    <span data-ttu-id="d919a-127">Сбор криминалистической экспертизы</span><span class="sxs-lookup"><span data-stu-id="d919a-127">Collect   forensics</span></span>   <br><span data-ttu-id="d919a-128">Изолировать машину</span><span class="sxs-lookup"><span data-stu-id="d919a-128">Isolate   machine</span></span><br><span data-ttu-id="d919a-129">Ограничение выполнения кода</span><span class="sxs-lookup"><span data-stu-id="d919a-129">Restrict   code execution</span></span><br>  <span data-ttu-id="d919a-130">Машина сканирования</span><span class="sxs-lookup"><span data-stu-id="d919a-130">Scan   machine</span></span><br>  <span data-ttu-id="d919a-131">Offboard machine</span><span class="sxs-lookup"><span data-stu-id="d919a-131">Offboard   machine</span></span><br>   <span data-ttu-id="d919a-132">Остановка и карантин</span><span class="sxs-lookup"><span data-stu-id="d919a-132">Stop And   Quarantine</span></span><br>   <span data-ttu-id="d919a-133">Запуск ответа в прямом эфире на определенном компьютере</span><span class="sxs-lookup"><span data-stu-id="d919a-133">Run live   response on a specific machine</span></span>    |
|    <br><span data-ttu-id="d919a-134">Делегированная (работа или учетная запись школы)</span><span class="sxs-lookup"><span data-stu-id="d919a-134">Delegated   (work or school account)</span></span>    |    <span data-ttu-id="d919a-135">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="d919a-135">Machine.CollectForensic</span></span><br>   <span data-ttu-id="d919a-136">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="d919a-136">Machine.Isolate</span></span>    <br><span data-ttu-id="d919a-137">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="d919a-137">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="d919a-138">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="d919a-138">Machine.Scan</span></span><br>   <span data-ttu-id="d919a-139">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="d919a-139">Machine.Offboard</span></span><br>   <span data-ttu-id="d919a-140">Machine.StopAndQuarantineMachine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="d919a-140">Machine.StopAndQuarantineMachine.LiveResponse</span></span>    |    <span data-ttu-id="d919a-141">Сбор криминалистической экспертизы</span><span class="sxs-lookup"><span data-stu-id="d919a-141">Collect   forensics</span></span><br>   <span data-ttu-id="d919a-142">Изолировать машину</span><span class="sxs-lookup"><span data-stu-id="d919a-142">Isolate   machine</span></span><br>  <span data-ttu-id="d919a-143">Ограничение выполнения кода</span><span class="sxs-lookup"><span data-stu-id="d919a-143">Restrict   code execution</span></span><br> <span data-ttu-id="d919a-144">Машина сканирования</span><span class="sxs-lookup"><span data-stu-id="d919a-144">Scan   machine</span></span><br><span data-ttu-id="d919a-145">Offboard machine</span><span class="sxs-lookup"><span data-stu-id="d919a-145">Offboard   machine</span></span><br> <span data-ttu-id="d919a-146">Остановка и карантин</span><span class="sxs-lookup"><span data-stu-id="d919a-146">Stop And   Quarantine</span></span><br> <span data-ttu-id="d919a-147">Запуск ответа в прямом эфире на определенном компьютере</span><span class="sxs-lookup"><span data-stu-id="d919a-147">Run live   response on a specific machine</span></span>    |


## <a name="http-request"></a><span data-ttu-id="d919a-148">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="d919a-148">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a><span data-ttu-id="d919a-149">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="d919a-149">Request headers</span></span>

| <span data-ttu-id="d919a-150">Имя</span><span class="sxs-lookup"><span data-stu-id="d919a-150">Name</span></span>      | <span data-ttu-id="d919a-151">Тип</span><span class="sxs-lookup"><span data-stu-id="d919a-151">Type</span></span> | <span data-ttu-id="d919a-152">Описание</span><span class="sxs-lookup"><span data-stu-id="d919a-152">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="d919a-153">Authorization</span><span class="sxs-lookup"><span data-stu-id="d919a-153">Authorization</span></span> | <span data-ttu-id="d919a-154">String</span><span class="sxs-lookup"><span data-stu-id="d919a-154">String</span></span>   | <span data-ttu-id="d919a-p103">Bearer {токен}. Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d919a-p103">Bearer {token}. Required.</span></span>   |
| <span data-ttu-id="d919a-157">Content-Type</span><span class="sxs-lookup"><span data-stu-id="d919a-157">Content-Type</span></span>  | <span data-ttu-id="d919a-158">string</span><span class="sxs-lookup"><span data-stu-id="d919a-158">string</span></span>   | <span data-ttu-id="d919a-p104">application/json. Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d919a-p104">application/json. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="d919a-161">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="d919a-161">Request body</span></span>

| <span data-ttu-id="d919a-162">Параметр</span><span class="sxs-lookup"><span data-stu-id="d919a-162">Parameter</span></span> | <span data-ttu-id="d919a-163">Тип</span><span class="sxs-lookup"><span data-stu-id="d919a-163">Type</span></span> | <span data-ttu-id="d919a-164">Описание</span><span class="sxs-lookup"><span data-stu-id="d919a-164">Description</span></span>                        |
|---------------|----------|----------------------------------------|
| <span data-ttu-id="d919a-165">Comment</span><span class="sxs-lookup"><span data-stu-id="d919a-165">Comment</span></span>       | <span data-ttu-id="d919a-166">String</span><span class="sxs-lookup"><span data-stu-id="d919a-166">String</span></span>   | <span data-ttu-id="d919a-167">Комментарий для связи с действием отмены.</span><span class="sxs-lookup"><span data-stu-id="d919a-167">Comment to associate with the cancellation action.</span></span>  |

## <a name="response"></a><span data-ttu-id="d919a-168">Отклик</span><span class="sxs-lookup"><span data-stu-id="d919a-168">Response</span></span>

<span data-ttu-id="d919a-169">В случае успешной работы этот метод возвращает код ответа 200 Ok с объектом Machine Action.</span><span class="sxs-lookup"><span data-stu-id="d919a-169">If successful, this method returns 200, Ok response code with a Machine Action entity.</span></span> <span data-ttu-id="d919a-170">Если объект действия машины с указанным id не найден - 404 Не найден.</span><span class="sxs-lookup"><span data-stu-id="d919a-170">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="d919a-171">Пример</span><span class="sxs-lookup"><span data-stu-id="d919a-171">Example</span></span>

<span data-ttu-id="d919a-172">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="d919a-172">**Request**</span></span>

<span data-ttu-id="d919a-173">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="d919a-173">Here is an example of the request.</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a><span data-ttu-id="d919a-174">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="d919a-174">Related topic</span></span>

- [<span data-ttu-id="d919a-175">Получите API действий машины</span><span class="sxs-lookup"><span data-stu-id="d919a-175">Get machine action API</span></span>](get-machineaction-object.md)