---
title: Освобождение устройства из API изоляции
description: Используйте этот API для создания вызовов, связанных с освобождением устройства из изоляции.
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
ms.technology: mde
ms.openlocfilehash: 036eb6f589c13fb9232557c45619829149179148
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199337"
---
# <a name="release-device-from-isolation-api"></a><span data-ttu-id="676c0-104">Освобождение устройства из API изоляции</span><span class="sxs-lookup"><span data-stu-id="676c0-104">Release device from isolation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="676c0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="676c0-105">**Applies to:**</span></span> 
- [<span data-ttu-id="676c0-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="676c0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="676c0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="676c0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="676c0-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="676c0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="676c0-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="676c0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="676c0-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="676c0-110">API description</span></span>
<span data-ttu-id="676c0-111">Отмена изоляции устройства.</span><span class="sxs-lookup"><span data-stu-id="676c0-111">Undo isolation of a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="676c0-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="676c0-112">Limitations</span></span>
1. <span data-ttu-id="676c0-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="676c0-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="676c0-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="676c0-114">Permissions</span></span>
<span data-ttu-id="676c0-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="676c0-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="676c0-116">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="676c0-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="676c0-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="676c0-117">Permission type</span></span> |   <span data-ttu-id="676c0-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="676c0-118">Permission</span></span>  |   <span data-ttu-id="676c0-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="676c0-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="676c0-120">Application</span><span class="sxs-lookup"><span data-stu-id="676c0-120">Application</span></span> |   <span data-ttu-id="676c0-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="676c0-121">Machine.Isolate</span></span> |   <span data-ttu-id="676c0-122">'Isolate machine'</span><span class="sxs-lookup"><span data-stu-id="676c0-122">'Isolate machine'</span></span>
<span data-ttu-id="676c0-123">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="676c0-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="676c0-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="676c0-124">Machine.Isolate</span></span> |   <span data-ttu-id="676c0-125">'Isolate machine'</span><span class="sxs-lookup"><span data-stu-id="676c0-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="676c0-126">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="676c0-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="676c0-127">У пользователя должно быть по крайней мере следующее разрешение на роль: "Активные действия по исправлению" (см. дополнительные сведения о создании и управлении ролями) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="676c0-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="676c0-128">Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="676c0-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="676c0-129">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="676c0-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unisolate
```

## <a name="request-headers"></a><span data-ttu-id="676c0-130">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="676c0-130">Request headers</span></span>

<span data-ttu-id="676c0-131">Имя</span><span class="sxs-lookup"><span data-stu-id="676c0-131">Name</span></span> | <span data-ttu-id="676c0-132">Тип</span><span class="sxs-lookup"><span data-stu-id="676c0-132">Type</span></span> | <span data-ttu-id="676c0-133">Описание</span><span class="sxs-lookup"><span data-stu-id="676c0-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="676c0-134">Авторизация</span><span class="sxs-lookup"><span data-stu-id="676c0-134">Authorization</span></span> | <span data-ttu-id="676c0-135">Строка</span><span class="sxs-lookup"><span data-stu-id="676c0-135">String</span></span> | <span data-ttu-id="676c0-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="676c0-136">Bearer {token}.</span></span> <span data-ttu-id="676c0-137">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="676c0-137">**Required**.</span></span>
<span data-ttu-id="676c0-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="676c0-138">Content-Type</span></span> | <span data-ttu-id="676c0-139">string</span><span class="sxs-lookup"><span data-stu-id="676c0-139">string</span></span> | <span data-ttu-id="676c0-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="676c0-140">application/json.</span></span> <span data-ttu-id="676c0-141">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="676c0-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="676c0-142">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="676c0-142">Request body</span></span>
<span data-ttu-id="676c0-143">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="676c0-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="676c0-144">Параметр</span><span class="sxs-lookup"><span data-stu-id="676c0-144">Parameter</span></span> | <span data-ttu-id="676c0-145">Тип</span><span class="sxs-lookup"><span data-stu-id="676c0-145">Type</span></span>    | <span data-ttu-id="676c0-146">Описание</span><span class="sxs-lookup"><span data-stu-id="676c0-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="676c0-147">Comment</span><span class="sxs-lookup"><span data-stu-id="676c0-147">Comment</span></span> |   <span data-ttu-id="676c0-148">String</span><span class="sxs-lookup"><span data-stu-id="676c0-148">String</span></span> |    <span data-ttu-id="676c0-149">Комментарий для связи с действием.</span><span class="sxs-lookup"><span data-stu-id="676c0-149">Comment to associate with the action.</span></span> <span data-ttu-id="676c0-150">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="676c0-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="676c0-151">Отклик</span><span class="sxs-lookup"><span data-stu-id="676c0-151">Response</span></span>
<span data-ttu-id="676c0-152">В случае успешной работы этот метод возвращает 201 — созданный код ответа и действие машины [в](machineaction.md) тексте отклика.</span><span class="sxs-lookup"><span data-stu-id="676c0-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="676c0-153">Пример</span><span class="sxs-lookup"><span data-stu-id="676c0-153">Example</span></span>

<span data-ttu-id="676c0-154">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="676c0-154">**Request**</span></span>

<span data-ttu-id="676c0-155">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="676c0-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unisolate 
```

```json
{
  "Comment": "Unisolate machine since it was clean and validated"
}

```


- <span data-ttu-id="676c0-156">Чтобы изолировать устройство, см. [в ленте Isolate device.](isolate-machine.md)</span><span class="sxs-lookup"><span data-stu-id="676c0-156">To isolate a device, see [Isolate device](isolate-machine.md).</span></span>

