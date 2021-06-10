---
title: API предупреждений о пакетном обновлении
description: Узнайте, как обновить оповещения Microsoft Defender для конечных точек в пакете с помощью этого API. Можно обновить свойства status, determination, classification и assignedTo.
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
ms.technology: mde
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167088"
---
# <a name="batch-update-alerts"></a><span data-ttu-id="8db3d-105">Пакетные оповещения об обновлении</span><span class="sxs-lookup"><span data-stu-id="8db3d-105">Batch update alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8db3d-106">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="8db3d-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="8db3d-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="8db3d-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8db3d-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="8db3d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="8db3d-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="8db3d-109">API description</span></span>
<span data-ttu-id="8db3d-110">Обновляет свойства пакета существующих [оповещений.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="8db3d-110">Updates properties of a batch of existing [Alerts](alerts.md).</span></span>
<br><span data-ttu-id="8db3d-111">Отправка **комментариев** доступна с свойствами или без обновления.</span><span class="sxs-lookup"><span data-stu-id="8db3d-111">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="8db3d-112">Updatable свойства: `status` , `determination` и `classification` `assignedTo` .</span><span class="sxs-lookup"><span data-stu-id="8db3d-112">Updatable properties are: `status`, `determination`, `classification` and `assignedTo`.</span></span>


## <a name="limitations"></a><span data-ttu-id="8db3d-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="8db3d-113">Limitations</span></span>
1. <span data-ttu-id="8db3d-114">Можно обновить оповещения, доступные в API.</span><span class="sxs-lookup"><span data-stu-id="8db3d-114">You can update alerts that are available in the API.</span></span> <span data-ttu-id="8db3d-115">Дополнительные [сведения см. в](get-alerts.md) списке Оповещений.</span><span class="sxs-lookup"><span data-stu-id="8db3d-115">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="8db3d-116">Ограничения скорости для этого API : 10 вызовов в минуту и 500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="8db3d-116">Rate limitations for this API are 10 calls per minute and 500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="8db3d-117">Разрешения</span><span class="sxs-lookup"><span data-stu-id="8db3d-117">Permissions</span></span>
<span data-ttu-id="8db3d-118">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="8db3d-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8db3d-119">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8db3d-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8db3d-120">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="8db3d-120">Permission type</span></span> |   <span data-ttu-id="8db3d-121">Разрешение</span><span class="sxs-lookup"><span data-stu-id="8db3d-121">Permission</span></span>  |   <span data-ttu-id="8db3d-122">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="8db3d-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8db3d-123">Приложение</span><span class="sxs-lookup"><span data-stu-id="8db3d-123">Application</span></span> |   <span data-ttu-id="8db3d-124">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8db3d-124">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="8db3d-125">'Read and write all alerts'</span><span class="sxs-lookup"><span data-stu-id="8db3d-125">'Read and write all alerts'</span></span>
<span data-ttu-id="8db3d-126">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="8db3d-126">Delegated (work or school account)</span></span> | <span data-ttu-id="8db3d-127">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8db3d-127">Alert.ReadWrite</span></span> | <span data-ttu-id="8db3d-128">'Read and write alerts'</span><span class="sxs-lookup"><span data-stu-id="8db3d-128">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="8db3d-129">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="8db3d-129">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="8db3d-130">У пользователя должно быть по крайней мере следующее разрешение на роль: "Оповещение о расследовании" (см. в рублях [Создание](user-roles.md) ролей и управление ими для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="8db3d-130">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="8db3d-131">Пользователь должен иметь доступ к устройству, связанному с оповещением, на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="8db3d-131">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="8db3d-132">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="8db3d-132">HTTP request</span></span>
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a><span data-ttu-id="8db3d-133">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="8db3d-133">Request headers</span></span>

<span data-ttu-id="8db3d-134">Имя</span><span class="sxs-lookup"><span data-stu-id="8db3d-134">Name</span></span> | <span data-ttu-id="8db3d-135">Тип</span><span class="sxs-lookup"><span data-stu-id="8db3d-135">Type</span></span> | <span data-ttu-id="8db3d-136">Описание</span><span class="sxs-lookup"><span data-stu-id="8db3d-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="8db3d-137">Авторизация</span><span class="sxs-lookup"><span data-stu-id="8db3d-137">Authorization</span></span> | <span data-ttu-id="8db3d-138">String</span><span class="sxs-lookup"><span data-stu-id="8db3d-138">String</span></span> | <span data-ttu-id="8db3d-139">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8db3d-139">Bearer {token}.</span></span> <span data-ttu-id="8db3d-140">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="8db3d-140">**Required**.</span></span>
<span data-ttu-id="8db3d-141">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8db3d-141">Content-Type</span></span> | <span data-ttu-id="8db3d-142">String</span><span class="sxs-lookup"><span data-stu-id="8db3d-142">String</span></span> | <span data-ttu-id="8db3d-143">application/json.</span><span class="sxs-lookup"><span data-stu-id="8db3d-143">application/json.</span></span> <span data-ttu-id="8db3d-144">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="8db3d-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="8db3d-145">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="8db3d-145">Request body</span></span>
<span data-ttu-id="8db3d-146">В теле запроса поставляем ID-данные оповещений, которые необходимо обновить, и значения соответствующих полей, которые необходимо обновить для этих оповещений.</span><span class="sxs-lookup"><span data-stu-id="8db3d-146">In the request body, supply the IDs of the alerts to be updated and the values of the relevant fields that you wish to update for these alerts.</span></span>
<br><span data-ttu-id="8db3d-147">Предыдущие значения существующих свойств, не включенных в текст запроса, останутся прежними или будут повторно вычислены с учетом измененных значений других свойств.</span><span class="sxs-lookup"><span data-stu-id="8db3d-147">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="8db3d-148">Для достижения оптимальной производительности не следует включать существующие значения, которые не изменились.</span><span class="sxs-lookup"><span data-stu-id="8db3d-148">For best performance you shouldn't include existing values that haven't changed.</span></span>

<span data-ttu-id="8db3d-149">Свойство</span><span class="sxs-lookup"><span data-stu-id="8db3d-149">Property</span></span> | <span data-ttu-id="8db3d-150">Тип</span><span class="sxs-lookup"><span data-stu-id="8db3d-150">Type</span></span> | <span data-ttu-id="8db3d-151">Описание</span><span class="sxs-lookup"><span data-stu-id="8db3d-151">Description</span></span>
:---|:---|:---
<span data-ttu-id="8db3d-152">alertIds</span><span class="sxs-lookup"><span data-stu-id="8db3d-152">alertIds</span></span> | <span data-ttu-id="8db3d-153">Строка &lt; списка&gt;</span><span class="sxs-lookup"><span data-stu-id="8db3d-153">List&lt;String&gt;</span></span>| <span data-ttu-id="8db3d-154">Список ID-списков оповещений, которые необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="8db3d-154">A list of the IDs of the alerts to be updated.</span></span> <span data-ttu-id="8db3d-155">**Required**</span><span class="sxs-lookup"><span data-stu-id="8db3d-155">**Required**</span></span>
<span data-ttu-id="8db3d-156">status</span><span class="sxs-lookup"><span data-stu-id="8db3d-156">status</span></span> | <span data-ttu-id="8db3d-157">String</span><span class="sxs-lookup"><span data-stu-id="8db3d-157">String</span></span> | <span data-ttu-id="8db3d-158">Указывает обновленный статус указанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="8db3d-158">Specifies the updated status of the specified alerts.</span></span> <span data-ttu-id="8db3d-159">Значения свойств: "New", "InProgress" и "Resolved".</span><span class="sxs-lookup"><span data-stu-id="8db3d-159">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="8db3d-160">assignedTo</span><span class="sxs-lookup"><span data-stu-id="8db3d-160">assignedTo</span></span> | <span data-ttu-id="8db3d-161">String</span><span class="sxs-lookup"><span data-stu-id="8db3d-161">String</span></span> | <span data-ttu-id="8db3d-162">Владелец указанных оповещений</span><span class="sxs-lookup"><span data-stu-id="8db3d-162">Owner of the specified alerts</span></span>
<span data-ttu-id="8db3d-163">classification</span><span class="sxs-lookup"><span data-stu-id="8db3d-163">classification</span></span> | <span data-ttu-id="8db3d-164">String</span><span class="sxs-lookup"><span data-stu-id="8db3d-164">String</span></span> | <span data-ttu-id="8db3d-165">Указывает спецификацию указанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="8db3d-165">Specifies the specification of the specified alerts.</span></span> <span data-ttu-id="8db3d-166">Значения свойств: "Неизвестный", "FalsePositive", "TruePositive".</span><span class="sxs-lookup"><span data-stu-id="8db3d-166">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="8db3d-167">определение</span><span class="sxs-lookup"><span data-stu-id="8db3d-167">determination</span></span> | <span data-ttu-id="8db3d-168">String</span><span class="sxs-lookup"><span data-stu-id="8db3d-168">String</span></span> | <span data-ttu-id="8db3d-169">Указывает определение указанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="8db3d-169">Specifies the determination of the specified alerts.</span></span> <span data-ttu-id="8db3d-170">Значения свойств: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other"</span><span class="sxs-lookup"><span data-stu-id="8db3d-170">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="8db3d-171">comment</span><span class="sxs-lookup"><span data-stu-id="8db3d-171">comment</span></span> | <span data-ttu-id="8db3d-172">String</span><span class="sxs-lookup"><span data-stu-id="8db3d-172">String</span></span> | <span data-ttu-id="8db3d-173">Комментарий, который необходимо добавить в указанные оповещения.</span><span class="sxs-lookup"><span data-stu-id="8db3d-173">Comment to be added to the specified alerts.</span></span>

## <a name="response"></a><span data-ttu-id="8db3d-174">Отклик</span><span class="sxs-lookup"><span data-stu-id="8db3d-174">Response</span></span>
<span data-ttu-id="8db3d-175">В случае успешной работы этот метод возвращает 200 ОК с пустым телом отклика.</span><span class="sxs-lookup"><span data-stu-id="8db3d-175">If successful, this method returns 200 OK, with an empty response body.</span></span>


## <a name="example"></a><span data-ttu-id="8db3d-176">Пример</span><span class="sxs-lookup"><span data-stu-id="8db3d-176">Example</span></span>

<span data-ttu-id="8db3d-177">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="8db3d-177">**Request**</span></span>

<span data-ttu-id="8db3d-178">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="8db3d-178">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
