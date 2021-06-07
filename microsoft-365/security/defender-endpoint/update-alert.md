---
title: Обновление API объекта оповещения
description: Узнайте, как обновить оповещение Microsoft Defender для конечных точек с помощью этого API. Можно обновить свойства status, determination, classification и assignedTo.
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
ms.openlocfilehash: 043d423e1016d77cad4a175aa41718329f464252
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768933"
---
# <a name="update-alert"></a><span data-ttu-id="06d2d-105">Обновление оповещения</span><span class="sxs-lookup"><span data-stu-id="06d2d-105">Update alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="06d2d-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="06d2d-106">**Applies to:**</span></span>
- [<span data-ttu-id="06d2d-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="06d2d-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="06d2d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06d2d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="06d2d-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="06d2d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="06d2d-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="06d2d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="06d2d-111">Описание API</span><span class="sxs-lookup"><span data-stu-id="06d2d-111">API description</span></span>
<span data-ttu-id="06d2d-112">Обновляет свойства существующего [оповещения.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="06d2d-112">Updates properties of existing [Alert](alerts.md).</span></span>
<br><span data-ttu-id="06d2d-113">Отправка **комментариев** доступна с свойствами или без обновления.</span><span class="sxs-lookup"><span data-stu-id="06d2d-113">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="06d2d-114">Updatable свойства: ```status``` , ```determination``` и ```classification``` ```assignedTo``` .</span><span class="sxs-lookup"><span data-stu-id="06d2d-114">Updatable properties are: ```status```, ```determination```, ```classification``` and ```assignedTo```.</span></span>


## <a name="limitations"></a><span data-ttu-id="06d2d-115">Ограничения</span><span class="sxs-lookup"><span data-stu-id="06d2d-115">Limitations</span></span>
1. <span data-ttu-id="06d2d-116">Вы можете обновлять оповещения, доступные в API.</span><span class="sxs-lookup"><span data-stu-id="06d2d-116">You can update alerts that available in the API.</span></span> <span data-ttu-id="06d2d-117">Дополнительные [сведения см. в](get-alerts.md) списке Оповещений.</span><span class="sxs-lookup"><span data-stu-id="06d2d-117">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="06d2d-118">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="06d2d-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="06d2d-119">Разрешения</span><span class="sxs-lookup"><span data-stu-id="06d2d-119">Permissions</span></span>
<span data-ttu-id="06d2d-120">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="06d2d-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="06d2d-121">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="06d2d-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="06d2d-122">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="06d2d-122">Permission type</span></span> |   <span data-ttu-id="06d2d-123">Разрешение</span><span class="sxs-lookup"><span data-stu-id="06d2d-123">Permission</span></span>  |   <span data-ttu-id="06d2d-124">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="06d2d-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="06d2d-125">Приложение</span><span class="sxs-lookup"><span data-stu-id="06d2d-125">Application</span></span> |   <span data-ttu-id="06d2d-126">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="06d2d-126">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="06d2d-127">'Read and write all alerts'</span><span class="sxs-lookup"><span data-stu-id="06d2d-127">'Read and write all alerts'</span></span>
<span data-ttu-id="06d2d-128">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="06d2d-128">Delegated (work or school account)</span></span> | <span data-ttu-id="06d2d-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="06d2d-129">Alert.ReadWrite</span></span> | <span data-ttu-id="06d2d-130">'Read and write alerts'</span><span class="sxs-lookup"><span data-stu-id="06d2d-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="06d2d-131">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="06d2d-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="06d2d-132">У пользователя должно быть по крайней мере следующее разрешение на роль: "Оповещение о расследовании" (см. в рублях [Создание](user-roles.md) ролей и управление ими для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="06d2d-132">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="06d2d-133">Пользователь должен иметь доступ к устройству, связанному с оповещением, на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="06d2d-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="06d2d-134">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="06d2d-134">HTTP request</span></span>
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="06d2d-135">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="06d2d-135">Request headers</span></span>

<span data-ttu-id="06d2d-136">Имя</span><span class="sxs-lookup"><span data-stu-id="06d2d-136">Name</span></span> | <span data-ttu-id="06d2d-137">Тип</span><span class="sxs-lookup"><span data-stu-id="06d2d-137">Type</span></span> | <span data-ttu-id="06d2d-138">Описание</span><span class="sxs-lookup"><span data-stu-id="06d2d-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="06d2d-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="06d2d-139">Authorization</span></span> | <span data-ttu-id="06d2d-140">String</span><span class="sxs-lookup"><span data-stu-id="06d2d-140">String</span></span> | <span data-ttu-id="06d2d-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="06d2d-141">Bearer {token}.</span></span> <span data-ttu-id="06d2d-142">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="06d2d-142">**Required**.</span></span>
<span data-ttu-id="06d2d-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="06d2d-143">Content-Type</span></span> | <span data-ttu-id="06d2d-144">String</span><span class="sxs-lookup"><span data-stu-id="06d2d-144">String</span></span> | <span data-ttu-id="06d2d-145">application/json.</span><span class="sxs-lookup"><span data-stu-id="06d2d-145">application/json.</span></span> <span data-ttu-id="06d2d-146">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="06d2d-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="06d2d-147">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="06d2d-147">Request body</span></span>
<span data-ttu-id="06d2d-148">В теле запроса укажи значения для соответствующих полей, которые должны быть обновлены.</span><span class="sxs-lookup"><span data-stu-id="06d2d-148">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="06d2d-149">Предыдущие значения существующих свойств, не включенных в текст запроса, будут сохранены или вычислены повторно с учетом изменений, внесенных в значения других свойств.</span><span class="sxs-lookup"><span data-stu-id="06d2d-149">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="06d2d-150">Для лучшей производительности не следует включать существующие значения, которые не изменились.</span><span class="sxs-lookup"><span data-stu-id="06d2d-150">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="06d2d-151">Свойство</span><span class="sxs-lookup"><span data-stu-id="06d2d-151">Property</span></span> | <span data-ttu-id="06d2d-152">Тип</span><span class="sxs-lookup"><span data-stu-id="06d2d-152">Type</span></span> | <span data-ttu-id="06d2d-153">Описание</span><span class="sxs-lookup"><span data-stu-id="06d2d-153">Description</span></span>
:---|:---|:---
<span data-ttu-id="06d2d-154">status</span><span class="sxs-lookup"><span data-stu-id="06d2d-154">status</span></span> | <span data-ttu-id="06d2d-155">String</span><span class="sxs-lookup"><span data-stu-id="06d2d-155">String</span></span> | <span data-ttu-id="06d2d-156">Указывает текущее состояние оповещений.</span><span class="sxs-lookup"><span data-stu-id="06d2d-156">Specifies the current status of the alert.</span></span> <span data-ttu-id="06d2d-157">Значения свойств: "New", "InProgress" и "Resolved".</span><span class="sxs-lookup"><span data-stu-id="06d2d-157">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="06d2d-158">assignedTo</span><span class="sxs-lookup"><span data-stu-id="06d2d-158">assignedTo</span></span> | <span data-ttu-id="06d2d-159">String</span><span class="sxs-lookup"><span data-stu-id="06d2d-159">String</span></span> | <span data-ttu-id="06d2d-160">Владелец оповещений</span><span class="sxs-lookup"><span data-stu-id="06d2d-160">Owner of the alert</span></span>
<span data-ttu-id="06d2d-161">classification</span><span class="sxs-lookup"><span data-stu-id="06d2d-161">classification</span></span> | <span data-ttu-id="06d2d-162">String</span><span class="sxs-lookup"><span data-stu-id="06d2d-162">String</span></span> | <span data-ttu-id="06d2d-163">Указывает спецификацию оповещений.</span><span class="sxs-lookup"><span data-stu-id="06d2d-163">Specifies the specification of the alert.</span></span> <span data-ttu-id="06d2d-164">Значения свойств: "Неизвестный", "FalsePositive", "TruePositive".</span><span class="sxs-lookup"><span data-stu-id="06d2d-164">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="06d2d-165">определение</span><span class="sxs-lookup"><span data-stu-id="06d2d-165">determination</span></span> | <span data-ttu-id="06d2d-166">String</span><span class="sxs-lookup"><span data-stu-id="06d2d-166">String</span></span> | <span data-ttu-id="06d2d-167">Указывает определение оповещений.</span><span class="sxs-lookup"><span data-stu-id="06d2d-167">Specifies the determination of the alert.</span></span> <span data-ttu-id="06d2d-168">Значения свойств: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other"</span><span class="sxs-lookup"><span data-stu-id="06d2d-168">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="06d2d-169">comment</span><span class="sxs-lookup"><span data-stu-id="06d2d-169">comment</span></span> | <span data-ttu-id="06d2d-170">String</span><span class="sxs-lookup"><span data-stu-id="06d2d-170">String</span></span> | <span data-ttu-id="06d2d-171">Комментарий, который необходимо добавить в оповещение.</span><span class="sxs-lookup"><span data-stu-id="06d2d-171">Comment to be added to the alert.</span></span>

## <a name="response"></a><span data-ttu-id="06d2d-172">Отклик</span><span class="sxs-lookup"><span data-stu-id="06d2d-172">Response</span></span>
<span data-ttu-id="06d2d-173">В случае успешной работы этот метод возвращает [](alerts.md) 200 ОК, а объект оповещения в теле ответа с обновленными свойствами.</span><span class="sxs-lookup"><span data-stu-id="06d2d-173">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="06d2d-174">Если оповещение с указанным id не найдено - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="06d2d-174">If alert with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="06d2d-175">Пример</span><span class="sxs-lookup"><span data-stu-id="06d2d-175">Example</span></span>

<span data-ttu-id="06d2d-176">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="06d2d-176">**Request**</span></span>

<span data-ttu-id="06d2d-177">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="06d2d-177">Here is an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
