---
title: Ограничение API выполнения приложений
description: Используйте этот API для создания вызовов, связанных с ограничением выполнения приложения.
keywords: apis, graph api, supported apis, collect investigation package
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7195e91a3a9b7aef6977c925f2c8689d3e461815
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771577"
---
# <a name="restrict-app-execution-api"></a><span data-ttu-id="f751d-104">Ограничение API выполнения приложений</span><span class="sxs-lookup"><span data-stu-id="f751d-104">Restrict app execution API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f751d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f751d-105">**Applies to:**</span></span>
- [<span data-ttu-id="f751d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f751d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f751d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f751d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="f751d-108">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f751d-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f751d-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f751d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f751d-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f751d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f751d-111">Описание API</span><span class="sxs-lookup"><span data-stu-id="f751d-111">API description</span></span>
<span data-ttu-id="f751d-112">Ограничение выполнения всех приложений на устройстве, за исключением предопределяемого набора.</span><span class="sxs-lookup"><span data-stu-id="f751d-112">Restrict execution of all applications on the device except a predefined set.</span></span>


## <a name="limitations"></a><span data-ttu-id="f751d-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f751d-113">Limitations</span></span>
1. <span data-ttu-id="f751d-114">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="f751d-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="f751d-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="f751d-115">Permissions</span></span>
<span data-ttu-id="f751d-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="f751d-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f751d-117">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f751d-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f751d-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="f751d-118">Permission type</span></span> |   <span data-ttu-id="f751d-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="f751d-119">Permission</span></span>  |   <span data-ttu-id="f751d-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="f751d-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f751d-121">Приложение</span><span class="sxs-lookup"><span data-stu-id="f751d-121">Application</span></span> |   <span data-ttu-id="f751d-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="f751d-122">Machine.RestrictExecution</span></span> | <span data-ttu-id="f751d-123">"Ограничение выполнения кода"</span><span class="sxs-lookup"><span data-stu-id="f751d-123">'Restrict code execution'</span></span>
<span data-ttu-id="f751d-124">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="f751d-124">Delegated (work or school account)</span></span> | <span data-ttu-id="f751d-125">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="f751d-125">Machine.RestrictExecution</span></span> | <span data-ttu-id="f751d-126">"Ограничение выполнения кода"</span><span class="sxs-lookup"><span data-stu-id="f751d-126">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="f751d-127">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="f751d-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f751d-128">У пользователя должно быть по крайней мере следующее разрешение на роль: "Активные действия по исправлению" (см. дополнительные сведения о создании и управлении ролями) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="f751d-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="f751d-129">Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="f751d-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f751d-130">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="f751d-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="f751d-131">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="f751d-131">Request headers</span></span>

<span data-ttu-id="f751d-132">Имя</span><span class="sxs-lookup"><span data-stu-id="f751d-132">Name</span></span> | <span data-ttu-id="f751d-133">Тип</span><span class="sxs-lookup"><span data-stu-id="f751d-133">Type</span></span> | <span data-ttu-id="f751d-134">Описание</span><span class="sxs-lookup"><span data-stu-id="f751d-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="f751d-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="f751d-135">Authorization</span></span> | <span data-ttu-id="f751d-136">String</span><span class="sxs-lookup"><span data-stu-id="f751d-136">String</span></span> | <span data-ttu-id="f751d-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f751d-137">Bearer {token}.</span></span> <span data-ttu-id="f751d-138">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="f751d-138">**Required**.</span></span>
<span data-ttu-id="f751d-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="f751d-139">Content-Type</span></span> | <span data-ttu-id="f751d-140">string</span><span class="sxs-lookup"><span data-stu-id="f751d-140">string</span></span> | <span data-ttu-id="f751d-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="f751d-141">application/json.</span></span> <span data-ttu-id="f751d-142">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="f751d-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f751d-143">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="f751d-143">Request body</span></span>
<span data-ttu-id="f751d-144">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="f751d-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="f751d-145">Параметр</span><span class="sxs-lookup"><span data-stu-id="f751d-145">Parameter</span></span> | <span data-ttu-id="f751d-146">Тип</span><span class="sxs-lookup"><span data-stu-id="f751d-146">Type</span></span>    | <span data-ttu-id="f751d-147">Описание</span><span class="sxs-lookup"><span data-stu-id="f751d-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="f751d-148">Comment</span><span class="sxs-lookup"><span data-stu-id="f751d-148">Comment</span></span> |   <span data-ttu-id="f751d-149">String</span><span class="sxs-lookup"><span data-stu-id="f751d-149">String</span></span> |    <span data-ttu-id="f751d-150">Комментарий для связи с действием.</span><span class="sxs-lookup"><span data-stu-id="f751d-150">Comment to associate with the action.</span></span> <span data-ttu-id="f751d-151">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="f751d-151">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="f751d-152">Отклик</span><span class="sxs-lookup"><span data-stu-id="f751d-152">Response</span></span>
<span data-ttu-id="f751d-153">В случае успешной работы этот метод возвращает 201 — созданный код ответа и действие машины [в](machineaction.md) тексте отклика.</span><span class="sxs-lookup"><span data-stu-id="f751d-153">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="f751d-154">Пример</span><span class="sxs-lookup"><span data-stu-id="f751d-154">Example</span></span>

<span data-ttu-id="f751d-155">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="f751d-155">**Request**</span></span>

<span data-ttu-id="f751d-156">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="f751d-156">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- <span data-ttu-id="f751d-157">Чтобы удалить ограничение выполнения кода с устройства, см. в [приложении Remove restriction.](unrestrict-code-execution.md)</span><span class="sxs-lookup"><span data-stu-id="f751d-157">To remove code execution restriction from a device, see [Remove app restriction](unrestrict-code-execution.md).</span></span>
