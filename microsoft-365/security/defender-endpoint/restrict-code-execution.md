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
ms.technology: mde
ms.openlocfilehash: 149f3aefd963f15eafa15030a322ec588c0615ed
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186787"
---
# <a name="restrict-app-execution-api"></a><span data-ttu-id="10c22-104">Ограничение API выполнения приложений</span><span class="sxs-lookup"><span data-stu-id="10c22-104">Restrict app execution API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="10c22-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="10c22-105">**Applies to:**</span></span>
- [<span data-ttu-id="10c22-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="10c22-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="10c22-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10c22-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="10c22-108">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="10c22-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="10c22-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="10c22-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="10c22-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="10c22-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="10c22-111">Описание API</span><span class="sxs-lookup"><span data-stu-id="10c22-111">API description</span></span>
<span data-ttu-id="10c22-112">Ограничение выполнения всех приложений на устройстве, за исключением предопределяемого набора.</span><span class="sxs-lookup"><span data-stu-id="10c22-112">Restrict execution of all applications on the device except a predefined set.</span></span>


## <a name="limitations"></a><span data-ttu-id="10c22-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="10c22-113">Limitations</span></span>
1. <span data-ttu-id="10c22-114">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="10c22-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="10c22-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="10c22-115">Permissions</span></span>
<span data-ttu-id="10c22-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="10c22-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="10c22-117">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="10c22-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="10c22-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="10c22-118">Permission type</span></span> |   <span data-ttu-id="10c22-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="10c22-119">Permission</span></span>  |   <span data-ttu-id="10c22-120">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="10c22-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="10c22-121">Приложение</span><span class="sxs-lookup"><span data-stu-id="10c22-121">Application</span></span> |   <span data-ttu-id="10c22-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="10c22-122">Machine.RestrictExecution</span></span> | <span data-ttu-id="10c22-123">"Ограничение выполнения кода"</span><span class="sxs-lookup"><span data-stu-id="10c22-123">'Restrict code execution'</span></span>
<span data-ttu-id="10c22-124">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="10c22-124">Delegated (work or school account)</span></span> | <span data-ttu-id="10c22-125">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="10c22-125">Machine.RestrictExecution</span></span> | <span data-ttu-id="10c22-126">"Ограничение выполнения кода"</span><span class="sxs-lookup"><span data-stu-id="10c22-126">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="10c22-127">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="10c22-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="10c22-128">У пользователя должно быть по крайней мере следующее разрешение на роль: "Активные действия по исправлению" (см. дополнительные сведения о создании и управлении ролями) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="10c22-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="10c22-129">Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="10c22-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="10c22-130">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="10c22-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="10c22-131">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="10c22-131">Request headers</span></span>

<span data-ttu-id="10c22-132">Имя</span><span class="sxs-lookup"><span data-stu-id="10c22-132">Name</span></span> | <span data-ttu-id="10c22-133">Тип</span><span class="sxs-lookup"><span data-stu-id="10c22-133">Type</span></span> | <span data-ttu-id="10c22-134">Описание</span><span class="sxs-lookup"><span data-stu-id="10c22-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="10c22-135">Авторизация</span><span class="sxs-lookup"><span data-stu-id="10c22-135">Authorization</span></span> | <span data-ttu-id="10c22-136">Строка</span><span class="sxs-lookup"><span data-stu-id="10c22-136">String</span></span> | <span data-ttu-id="10c22-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="10c22-137">Bearer {token}.</span></span> <span data-ttu-id="10c22-138">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="10c22-138">**Required**.</span></span>
<span data-ttu-id="10c22-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="10c22-139">Content-Type</span></span> | <span data-ttu-id="10c22-140">string</span><span class="sxs-lookup"><span data-stu-id="10c22-140">string</span></span> | <span data-ttu-id="10c22-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="10c22-141">application/json.</span></span> <span data-ttu-id="10c22-142">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="10c22-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="10c22-143">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="10c22-143">Request body</span></span>
<span data-ttu-id="10c22-144">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="10c22-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="10c22-145">Параметр</span><span class="sxs-lookup"><span data-stu-id="10c22-145">Parameter</span></span> | <span data-ttu-id="10c22-146">Тип</span><span class="sxs-lookup"><span data-stu-id="10c22-146">Type</span></span>    | <span data-ttu-id="10c22-147">Описание</span><span class="sxs-lookup"><span data-stu-id="10c22-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="10c22-148">Comment</span><span class="sxs-lookup"><span data-stu-id="10c22-148">Comment</span></span> |   <span data-ttu-id="10c22-149">String</span><span class="sxs-lookup"><span data-stu-id="10c22-149">String</span></span> |    <span data-ttu-id="10c22-150">Комментарий для связи с действием.</span><span class="sxs-lookup"><span data-stu-id="10c22-150">Comment to associate with the action.</span></span> <span data-ttu-id="10c22-151">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="10c22-151">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="10c22-152">Отклик</span><span class="sxs-lookup"><span data-stu-id="10c22-152">Response</span></span>
<span data-ttu-id="10c22-153">В случае успешной работы этот метод возвращает 201 — созданный код ответа и действие машины [в](machineaction.md) тексте отклика.</span><span class="sxs-lookup"><span data-stu-id="10c22-153">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="10c22-154">Пример</span><span class="sxs-lookup"><span data-stu-id="10c22-154">Example</span></span>

<span data-ttu-id="10c22-155">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="10c22-155">**Request**</span></span>

<span data-ttu-id="10c22-156">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="10c22-156">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- <span data-ttu-id="10c22-157">Чтобы удалить ограничение выполнения кода с устройства, см. в [приложении Remove restriction.](unrestrict-code-execution.md)</span><span class="sxs-lookup"><span data-stu-id="10c22-157">To remove code execution restriction from a device, see [Remove app restriction](unrestrict-code-execution.md).</span></span>
