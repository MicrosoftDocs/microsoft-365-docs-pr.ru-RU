---
title: Обновление API сущности машины
description: Узнайте, как обновить теги машин с помощью этого API. Вы можете обновить теги и свойства devicevalue.
keywords: apis, api graph, supported apis, get, alert, information, id
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985749"
---
# <a name="update-machine"></a><span data-ttu-id="530a4-105">Машина обновления</span><span class="sxs-lookup"><span data-stu-id="530a4-105">Update machine</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="530a4-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="530a4-106">**Applies to:**</span></span>
- [<span data-ttu-id="530a4-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="530a4-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="530a4-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="530a4-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="530a4-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="530a4-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="530a4-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="530a4-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="530a4-111">Описание API</span><span class="sxs-lookup"><span data-stu-id="530a4-111">API description</span></span>
<span data-ttu-id="530a4-112">Обновляет свойства существующей [машины.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="530a4-112">Updates properties of existing [Machine](machine.md).</span></span>
<br><span data-ttu-id="530a4-113">Updatable свойства: ```machineTags``` и ```deviceValue``` .</span><span class="sxs-lookup"><span data-stu-id="530a4-113">Updatable properties are: ```machineTags``` and ```deviceValue```.</span></span>


## <a name="limitations"></a><span data-ttu-id="530a4-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="530a4-114">Limitations</span></span>
1. <span data-ttu-id="530a4-115">Можно обновить машины, доступные в API.</span><span class="sxs-lookup"><span data-stu-id="530a4-115">You can update machines that are available in the API.</span></span> 
2. <span data-ttu-id="530a4-116">Машина обновления только привносят теги в коллекцию тегов.</span><span class="sxs-lookup"><span data-stu-id="530a4-116">Update machine only appends tags to the tag collection.</span></span> <span data-ttu-id="530a4-117">Если теги существуют, они должны быть включены в коллекцию тегов в теле.</span><span class="sxs-lookup"><span data-stu-id="530a4-117">If tags exist, they must be included in the tags collection in the body.</span></span>
3. <span data-ttu-id="530a4-118">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="530a4-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="530a4-119">Разрешения</span><span class="sxs-lookup"><span data-stu-id="530a4-119">Permissions</span></span>
<span data-ttu-id="530a4-120">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="530a4-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="530a4-121">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="530a4-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="530a4-122">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="530a4-122">Permission type</span></span> |   <span data-ttu-id="530a4-123">Разрешение</span><span class="sxs-lookup"><span data-stu-id="530a4-123">Permission</span></span>  |   <span data-ttu-id="530a4-124">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="530a4-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="530a4-125">Для приложения</span><span class="sxs-lookup"><span data-stu-id="530a4-125">Application</span></span> |   <span data-ttu-id="530a4-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="530a4-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="530a4-127">'Read and write machine information for all machines'</span><span class="sxs-lookup"><span data-stu-id="530a4-127">'Read and write machine information for all machines'</span></span>
<span data-ttu-id="530a4-128">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="530a4-128">Delegated (work or school account)</span></span> | <span data-ttu-id="530a4-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="530a4-129">Machine.ReadWrite</span></span> | <span data-ttu-id="530a4-130">'Read and write machine information'</span><span class="sxs-lookup"><span data-stu-id="530a4-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="530a4-131">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="530a4-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="530a4-132">У пользователя должно быть по крайней мере следующее разрешение на роль: "Оповещение о расследовании".</span><span class="sxs-lookup"><span data-stu-id="530a4-132">The user needs to have at least the following role permission: 'Alerts investigation'.</span></span> <span data-ttu-id="530a4-133">Дополнительные сведения см. в [дополнительных сведениях о создании и управлении ролями.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="530a4-133">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="530a4-134">Пользователь должен иметь доступ к устройству, связанному с оповещением, в зависимости от параметров группы устройств.</span><span class="sxs-lookup"><span data-stu-id="530a4-134">The user needs to have access to the device associated with the alert, based on device group settings.</span></span> <span data-ttu-id="530a4-135">Дополнительные сведения см. в [дополнительных сведениях о создании и управлении группами устройств.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="530a4-135">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="530a4-136">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="530a4-136">HTTP request</span></span>
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a><span data-ttu-id="530a4-137">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="530a4-137">Request headers</span></span>

<span data-ttu-id="530a4-138">Имя</span><span class="sxs-lookup"><span data-stu-id="530a4-138">Name</span></span> | <span data-ttu-id="530a4-139">Тип</span><span class="sxs-lookup"><span data-stu-id="530a4-139">Type</span></span> | <span data-ttu-id="530a4-140">Описание</span><span class="sxs-lookup"><span data-stu-id="530a4-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="530a4-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="530a4-141">Authorization</span></span> | <span data-ttu-id="530a4-142">String</span><span class="sxs-lookup"><span data-stu-id="530a4-142">String</span></span> | <span data-ttu-id="530a4-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="530a4-143">Bearer {token}.</span></span> <span data-ttu-id="530a4-144">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="530a4-144">**Required**.</span></span>
<span data-ttu-id="530a4-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="530a4-145">Content-Type</span></span> | <span data-ttu-id="530a4-146">String</span><span class="sxs-lookup"><span data-stu-id="530a4-146">String</span></span> | <span data-ttu-id="530a4-147">application/json.</span><span class="sxs-lookup"><span data-stu-id="530a4-147">application/json.</span></span> <span data-ttu-id="530a4-148">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="530a4-148">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="530a4-149">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="530a4-149">Request body</span></span>
<span data-ttu-id="530a4-150">В теле запроса укажи значения для соответствующих полей, которые должны быть обновлены.</span><span class="sxs-lookup"><span data-stu-id="530a4-150">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="530a4-151">Предыдущие значения существующих свойств, не включенных в текст запроса, будут сохранены или вычислены повторно с учетом изменений, внесенных в значения других свойств.</span><span class="sxs-lookup"><span data-stu-id="530a4-151">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="530a4-152">Для лучшей производительности не следует включать существующие значения, которые не изменились.</span><span class="sxs-lookup"><span data-stu-id="530a4-152">For best performance, you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="530a4-153">Свойство</span><span class="sxs-lookup"><span data-stu-id="530a4-153">Property</span></span> | <span data-ttu-id="530a4-154">Тип</span><span class="sxs-lookup"><span data-stu-id="530a4-154">Type</span></span> | <span data-ttu-id="530a4-155">Описание</span><span class="sxs-lookup"><span data-stu-id="530a4-155">Description</span></span>
:---|:---|:---
<span data-ttu-id="530a4-156">machineTags</span><span class="sxs-lookup"><span data-stu-id="530a4-156">machineTags</span></span> | <span data-ttu-id="530a4-157">Коллекция объектов string</span><span class="sxs-lookup"><span data-stu-id="530a4-157">String collection</span></span> | <span data-ttu-id="530a4-158">Набор [тегов](machine.md) машин.</span><span class="sxs-lookup"><span data-stu-id="530a4-158">Set of [machine](machine.md) tags.</span></span>
<span data-ttu-id="530a4-159">deviceValue</span><span class="sxs-lookup"><span data-stu-id="530a4-159">deviceValue</span></span> | <span data-ttu-id="530a4-160">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="530a4-160">Nullable Enum</span></span> | <span data-ttu-id="530a4-161">Значение [устройства](tvm-assign-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="530a4-161">The [value of the device](tvm-assign-device-value.md).</span></span> <span data-ttu-id="530a4-162">Возможные значения: "Нормальный", "Низкий" и "Высокий".</span><span class="sxs-lookup"><span data-stu-id="530a4-162">Possible values are: 'Normal', 'Low' and 'High'.</span></span>

## <a name="response"></a><span data-ttu-id="530a4-163">Отклик</span><span class="sxs-lookup"><span data-stu-id="530a4-163">Response</span></span>
<span data-ttu-id="530a4-164">В случае успешной работы этот метод возвращает [](machine.md) 200 ОК, а объект машины в теле ответа с обновленными свойствами.</span><span class="sxs-lookup"><span data-stu-id="530a4-164">If successful, this method returns 200 OK, and the [machine](machine.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="530a4-165">Если коллекция тегов машин в теле не содержит существующие теги машин - 400 Недействительный вход и сообщение, информирующие о отсутствующих тегах/s.</span><span class="sxs-lookup"><span data-stu-id="530a4-165">If machine tags collection in body doesn't contain existing machine tags - 400 Invalid Input and a message informing of the missing tag/s.</span></span>
<span data-ttu-id="530a4-166">Если машина с указанным ИД не найдена - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="530a4-166">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="530a4-167">Пример</span><span class="sxs-lookup"><span data-stu-id="530a4-167">Example</span></span>

<span data-ttu-id="530a4-168">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="530a4-168">**Request**</span></span>

<span data-ttu-id="530a4-169">Вот пример запроса.</span><span class="sxs-lookup"><span data-stu-id="530a4-169">Here's an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
