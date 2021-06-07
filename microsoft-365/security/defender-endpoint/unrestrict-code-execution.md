---
title: Удаление API ограничений приложений
description: Используйте этот API для создания вызовов, связанных с удалением ограничения из приложений при выполнении.
keywords: apis, api графа, поддерживаемые apis, удаление устройства из изоляции
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
ms.openlocfilehash: 989e44647a5f0661bfdefa184c6c26f4cdf2b456
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770881"
---
# <a name="remove-app-restriction-api"></a><span data-ttu-id="153e3-104">Удаление API ограничений приложений</span><span class="sxs-lookup"><span data-stu-id="153e3-104">Remove app restriction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="153e3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="153e3-105">**Applies to:**</span></span>
- [<span data-ttu-id="153e3-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="153e3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="153e3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="153e3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="153e3-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="153e3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="153e3-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="153e3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="153e3-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="153e3-110">API description</span></span>
<span data-ttu-id="153e3-111">Включить выполнение любого приложения на устройстве.</span><span class="sxs-lookup"><span data-stu-id="153e3-111">Enable execution of any application on the device.</span></span>


## <a name="limitations"></a><span data-ttu-id="153e3-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="153e3-112">Limitations</span></span>
1. <span data-ttu-id="153e3-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="153e3-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="153e3-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="153e3-114">Permissions</span></span>
<span data-ttu-id="153e3-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="153e3-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="153e3-116">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="153e3-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="153e3-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="153e3-117">Permission type</span></span> |   <span data-ttu-id="153e3-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="153e3-118">Permission</span></span>  |   <span data-ttu-id="153e3-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="153e3-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="153e3-120">Приложение</span><span class="sxs-lookup"><span data-stu-id="153e3-120">Application</span></span> |   <span data-ttu-id="153e3-121">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="153e3-121">Machine.RestrictExecution</span></span> | <span data-ttu-id="153e3-122">"Ограничение выполнения кода"</span><span class="sxs-lookup"><span data-stu-id="153e3-122">'Restrict code execution'</span></span>
<span data-ttu-id="153e3-123">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="153e3-123">Delegated (work or school account)</span></span> | <span data-ttu-id="153e3-124">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="153e3-124">Machine.RestrictExecution</span></span> | <span data-ttu-id="153e3-125">"Ограничение выполнения кода"</span><span class="sxs-lookup"><span data-stu-id="153e3-125">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="153e3-126">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="153e3-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="153e3-127">У пользователя должно быть по крайней мере следующее разрешение на роль: "Активные действия по исправлению" (см. дополнительные сведения о создании и управлении ролями) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="153e3-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="153e3-128">Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="153e3-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="153e3-129">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="153e3-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unrestrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="153e3-130">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="153e3-130">Request headers</span></span>
<span data-ttu-id="153e3-131">Имя</span><span class="sxs-lookup"><span data-stu-id="153e3-131">Name</span></span> | <span data-ttu-id="153e3-132">Тип</span><span class="sxs-lookup"><span data-stu-id="153e3-132">Type</span></span> | <span data-ttu-id="153e3-133">Описание</span><span class="sxs-lookup"><span data-stu-id="153e3-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="153e3-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="153e3-134">Authorization</span></span> | <span data-ttu-id="153e3-135">String</span><span class="sxs-lookup"><span data-stu-id="153e3-135">String</span></span> | <span data-ttu-id="153e3-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="153e3-136">Bearer {token}.</span></span> <span data-ttu-id="153e3-137">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="153e3-137">**Required**.</span></span>
<span data-ttu-id="153e3-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="153e3-138">Content-Type</span></span> | <span data-ttu-id="153e3-139">string</span><span class="sxs-lookup"><span data-stu-id="153e3-139">string</span></span> | <span data-ttu-id="153e3-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="153e3-140">application/json.</span></span> <span data-ttu-id="153e3-141">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="153e3-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="153e3-142">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="153e3-142">Request body</span></span>
<span data-ttu-id="153e3-143">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="153e3-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="153e3-144">Параметр</span><span class="sxs-lookup"><span data-stu-id="153e3-144">Parameter</span></span> | <span data-ttu-id="153e3-145">Тип</span><span class="sxs-lookup"><span data-stu-id="153e3-145">Type</span></span>    | <span data-ttu-id="153e3-146">Описание</span><span class="sxs-lookup"><span data-stu-id="153e3-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="153e3-147">Comment</span><span class="sxs-lookup"><span data-stu-id="153e3-147">Comment</span></span> |   <span data-ttu-id="153e3-148">String</span><span class="sxs-lookup"><span data-stu-id="153e3-148">String</span></span> | <span data-ttu-id="153e3-149">Комментарий для связи с действием.</span><span class="sxs-lookup"><span data-stu-id="153e3-149">Comment to associate with the action.</span></span> <span data-ttu-id="153e3-150">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="153e3-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="153e3-151">Отклик</span><span class="sxs-lookup"><span data-stu-id="153e3-151">Response</span></span>
<span data-ttu-id="153e3-152">В случае успешной работы этот метод возвращает 201 — созданный код ответа и действие машины [в](machineaction.md) тексте отклика.</span><span class="sxs-lookup"><span data-stu-id="153e3-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="153e3-153">Пример</span><span class="sxs-lookup"><span data-stu-id="153e3-153">Example</span></span>

<span data-ttu-id="153e3-154">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="153e3-154">**Request**</span></span>

<span data-ttu-id="153e3-155">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="153e3-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unrestrictCodeExecution 
```

```json
{
  "Comment": "Unrestrict code execution since machine was cleaned and validated"
}

```


<span data-ttu-id="153e3-156">Чтобы ограничить выполнение кода на устройстве, см. [в приложении Restrict execution.](restrict-code-execution.md)</span><span class="sxs-lookup"><span data-stu-id="153e3-156">To restrict code execution on a device, see [Restrict app execution](restrict-code-execution.md).</span></span>
