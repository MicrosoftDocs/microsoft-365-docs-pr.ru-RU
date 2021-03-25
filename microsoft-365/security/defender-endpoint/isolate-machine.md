---
title: API изолированной машины
description: Узнайте, как использовать API машины Isolate для изоляции устройства от доступа к внешней сети в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, isolate device
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
ms.openlocfilehash: b9c8d4da528ba065dc1b4a68ddaa816a1ad78c4a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187840"
---
# <a name="isolate-machine-api"></a><span data-ttu-id="c0590-104">API изолированной машины</span><span class="sxs-lookup"><span data-stu-id="c0590-104">Isolate machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c0590-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c0590-105">**Applies to:**</span></span>
- [<span data-ttu-id="c0590-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c0590-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c0590-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0590-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="c0590-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c0590-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c0590-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c0590-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c0590-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="c0590-110">API description</span></span>
<span data-ttu-id="c0590-111">Изолирует устройство от доступа к внешней сети.</span><span class="sxs-lookup"><span data-stu-id="c0590-111">Isolates a device from accessing external network.</span></span>


## <a name="limitations"></a><span data-ttu-id="c0590-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c0590-112">Limitations</span></span>
1. <span data-ttu-id="c0590-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="c0590-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="c0590-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="c0590-114">Permissions</span></span>
<span data-ttu-id="c0590-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="c0590-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c0590-116">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c0590-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c0590-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="c0590-117">Permission type</span></span> |   <span data-ttu-id="c0590-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="c0590-118">Permission</span></span>  |   <span data-ttu-id="c0590-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="c0590-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c0590-120">Приложение</span><span class="sxs-lookup"><span data-stu-id="c0590-120">Application</span></span> |   <span data-ttu-id="c0590-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="c0590-121">Machine.Isolate</span></span> |   <span data-ttu-id="c0590-122">'Isolate machine'</span><span class="sxs-lookup"><span data-stu-id="c0590-122">'Isolate machine'</span></span>
<span data-ttu-id="c0590-123">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="c0590-123">Delegated (work or school account)</span></span> | <span data-ttu-id="c0590-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="c0590-124">Machine.Isolate</span></span> |  <span data-ttu-id="c0590-125">'Isolate machine'</span><span class="sxs-lookup"><span data-stu-id="c0590-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="c0590-126">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="c0590-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c0590-127">У пользователя должно быть по крайней мере следующее разрешение на роль: "Активные действия по исправлению" (см. дополнительные сведения о создании и управлении ролями) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c0590-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="c0590-128">Пользователь должен иметь доступ к устройству на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="c0590-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="c0590-129">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="c0590-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a><span data-ttu-id="c0590-130">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="c0590-130">Request headers</span></span>

<span data-ttu-id="c0590-131">Имя</span><span class="sxs-lookup"><span data-stu-id="c0590-131">Name</span></span> | <span data-ttu-id="c0590-132">Тип</span><span class="sxs-lookup"><span data-stu-id="c0590-132">Type</span></span> | <span data-ttu-id="c0590-133">Описание</span><span class="sxs-lookup"><span data-stu-id="c0590-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="c0590-134">Авторизация</span><span class="sxs-lookup"><span data-stu-id="c0590-134">Authorization</span></span> | <span data-ttu-id="c0590-135">Строка</span><span class="sxs-lookup"><span data-stu-id="c0590-135">String</span></span> | <span data-ttu-id="c0590-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c0590-136">Bearer {token}.</span></span> <span data-ttu-id="c0590-137">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="c0590-137">**Required**.</span></span>
<span data-ttu-id="c0590-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c0590-138">Content-Type</span></span> | <span data-ttu-id="c0590-139">string</span><span class="sxs-lookup"><span data-stu-id="c0590-139">string</span></span> | <span data-ttu-id="c0590-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="c0590-140">application/json.</span></span> <span data-ttu-id="c0590-141">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="c0590-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c0590-142">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="c0590-142">Request body</span></span>
<span data-ttu-id="c0590-143">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="c0590-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c0590-144">Параметр</span><span class="sxs-lookup"><span data-stu-id="c0590-144">Parameter</span></span> | <span data-ttu-id="c0590-145">Тип</span><span class="sxs-lookup"><span data-stu-id="c0590-145">Type</span></span>    | <span data-ttu-id="c0590-146">Описание</span><span class="sxs-lookup"><span data-stu-id="c0590-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="c0590-147">Comment</span><span class="sxs-lookup"><span data-stu-id="c0590-147">Comment</span></span> |   <span data-ttu-id="c0590-148">String</span><span class="sxs-lookup"><span data-stu-id="c0590-148">String</span></span> |    <span data-ttu-id="c0590-149">Комментарий для связи с действием.</span><span class="sxs-lookup"><span data-stu-id="c0590-149">Comment to associate with the action.</span></span> <span data-ttu-id="c0590-150">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="c0590-150">**Required**.</span></span>
<span data-ttu-id="c0590-151">IsolationType</span><span class="sxs-lookup"><span data-stu-id="c0590-151">IsolationType</span></span>   | <span data-ttu-id="c0590-152">Строка</span><span class="sxs-lookup"><span data-stu-id="c0590-152">String</span></span> |  <span data-ttu-id="c0590-153">Тип изоляции.</span><span class="sxs-lookup"><span data-stu-id="c0590-153">Type of the isolation.</span></span> <span data-ttu-id="c0590-154">Допустимые значения: "Полный" или "Селективный".</span><span class="sxs-lookup"><span data-stu-id="c0590-154">Allowed values are: 'Full' or 'Selective'.</span></span>

<span data-ttu-id="c0590-155">**IsolationType** управляет типом изоляции для выполнения и может быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="c0590-155">**IsolationType** controls the type of isolation to perform and can be one of the following:</span></span>
- <span data-ttu-id="c0590-156">Полный — полная изоляция</span><span class="sxs-lookup"><span data-stu-id="c0590-156">Full – Full isolation</span></span>
- <span data-ttu-id="c0590-157">Селективный выбор : Ограничить доступ к сети только ограниченному набору приложений (дополнительные сведения см. в материале [Isolate devices from the network).](respond-machine-alerts.md#isolate-devices-from-the-network)</span><span class="sxs-lookup"><span data-stu-id="c0590-157">Selective – Restrict only limited set of applications from accessing the network (see [Isolate devices from the network](respond-machine-alerts.md#isolate-devices-from-the-network) for more details)</span></span>


## <a name="response"></a><span data-ttu-id="c0590-158">Отклик</span><span class="sxs-lookup"><span data-stu-id="c0590-158">Response</span></span>
<span data-ttu-id="c0590-159">В случае успешной работы этот метод возвращает 201 — созданный код ответа и действие машины [в](machineaction.md) тексте отклика.</span><span class="sxs-lookup"><span data-stu-id="c0590-159">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="c0590-160">Пример</span><span class="sxs-lookup"><span data-stu-id="c0590-160">Example</span></span>

<span data-ttu-id="c0590-161">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="c0590-161">**Request**</span></span>

<span data-ttu-id="c0590-162">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="c0590-162">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- <span data-ttu-id="c0590-163">Чтобы освободить устройство от изоляции, см. в выпуске устройства [из изоляции.](unisolate-machine.md)</span><span class="sxs-lookup"><span data-stu-id="c0590-163">To release a device from isolation, see [Release device from isolation](unisolate-machine.md).</span></span>
