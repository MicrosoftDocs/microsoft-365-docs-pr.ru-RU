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
ms.openlocfilehash: 80f88b31c1e07d1f40f3f58a1bd21b4a5c58c60b
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290211"
---
# <a name="batch-update-alerts"></a><span data-ttu-id="87ca3-105">Пакетные оповещения об обновлении</span><span class="sxs-lookup"><span data-stu-id="87ca3-105">Batch update alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="87ca3-106">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="87ca3-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="87ca3-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="87ca3-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="87ca3-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="87ca3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="87ca3-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="87ca3-109">API description</span></span>

<span data-ttu-id="87ca3-110">Обновляет свойства пакета существующих [оповещений.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="87ca3-110">Updates properties of a batch of existing [Alerts](alerts.md).</span></span>

<span data-ttu-id="87ca3-111">Отправка **комментариев** доступна с свойствами или без обновления.</span><span class="sxs-lookup"><span data-stu-id="87ca3-111">Submission of **comment** is available with or without updating properties.</span></span>

<span data-ttu-id="87ca3-112">Updatable свойства: `status` , `determination` и `classification` `assignedTo` .</span><span class="sxs-lookup"><span data-stu-id="87ca3-112">Updatable properties are: `status`, `determination`, `classification` and `assignedTo`.</span></span>

## <a name="limitations"></a><span data-ttu-id="87ca3-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="87ca3-113">Limitations</span></span>

1. <span data-ttu-id="87ca3-114">Можно обновить оповещения, доступные в API.</span><span class="sxs-lookup"><span data-stu-id="87ca3-114">You can update alerts that are available in the API.</span></span> <span data-ttu-id="87ca3-115">Дополнительные [сведения см. в](get-alerts.md) списке Оповещений.</span><span class="sxs-lookup"><span data-stu-id="87ca3-115">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="87ca3-116">Ограничения скорости для этого API : 10 вызовов в минуту и 500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="87ca3-116">Rate limitations for this API are 10 calls per minute and 500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="87ca3-117">Разрешения</span><span class="sxs-lookup"><span data-stu-id="87ca3-117">Permissions</span></span>

<span data-ttu-id="87ca3-118">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="87ca3-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="87ca3-119">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="87ca3-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="87ca3-120">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="87ca3-120">Permission type</span></span> | <span data-ttu-id="87ca3-121">Разрешение</span><span class="sxs-lookup"><span data-stu-id="87ca3-121">Permission</span></span> | <span data-ttu-id="87ca3-122">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="87ca3-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="87ca3-123">Application</span><span class="sxs-lookup"><span data-stu-id="87ca3-123">Application</span></span> | <span data-ttu-id="87ca3-124">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="87ca3-124">Alerts.ReadWrite.All</span></span> | <span data-ttu-id="87ca3-125">'Read and write all alerts'</span><span class="sxs-lookup"><span data-stu-id="87ca3-125">'Read and write all alerts'</span></span>
<span data-ttu-id="87ca3-126">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="87ca3-126">Delegated (work or school account)</span></span> | <span data-ttu-id="87ca3-127">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="87ca3-127">Alert.ReadWrite</span></span> | <span data-ttu-id="87ca3-128">'Read and write alerts'</span><span class="sxs-lookup"><span data-stu-id="87ca3-128">'Read and write alerts'</span></span>

> [!NOTE]
> <span data-ttu-id="87ca3-129">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="87ca3-129">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="87ca3-130">У пользователя должно быть по крайней мере следующее разрешение на роль: "Оповещение о расследовании" (см. в рублях [Создание](user-roles.md) ролей и управление ими для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="87ca3-130">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="87ca3-131">Пользователь должен иметь доступ к устройству, связанному с оповещением, на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="87ca3-131">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="87ca3-132">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="87ca3-132">HTTP request</span></span>

```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a><span data-ttu-id="87ca3-133">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="87ca3-133">Request headers</span></span>

<span data-ttu-id="87ca3-134">Имя</span><span class="sxs-lookup"><span data-stu-id="87ca3-134">Name</span></span> | <span data-ttu-id="87ca3-135">Тип</span><span class="sxs-lookup"><span data-stu-id="87ca3-135">Type</span></span> | <span data-ttu-id="87ca3-136">Описание</span><span class="sxs-lookup"><span data-stu-id="87ca3-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="87ca3-137">Authorization</span><span class="sxs-lookup"><span data-stu-id="87ca3-137">Authorization</span></span> | <span data-ttu-id="87ca3-138">Строка</span><span class="sxs-lookup"><span data-stu-id="87ca3-138">String</span></span> | <span data-ttu-id="87ca3-139">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="87ca3-139">Bearer {token}.</span></span> <span data-ttu-id="87ca3-140">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="87ca3-140">**Required**.</span></span>
<span data-ttu-id="87ca3-141">Content-Type</span><span class="sxs-lookup"><span data-stu-id="87ca3-141">Content-Type</span></span> | <span data-ttu-id="87ca3-142">String</span><span class="sxs-lookup"><span data-stu-id="87ca3-142">String</span></span> | <span data-ttu-id="87ca3-143">application/json.</span><span class="sxs-lookup"><span data-stu-id="87ca3-143">application/json.</span></span> <span data-ttu-id="87ca3-144">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="87ca3-144">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="87ca3-145">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="87ca3-145">Request body</span></span>

<span data-ttu-id="87ca3-146">В теле запроса поставляем ID-данные оповещений, которые необходимо обновить, и значения соответствующих полей, которые необходимо обновить для этих оповещений.</span><span class="sxs-lookup"><span data-stu-id="87ca3-146">In the request body, supply the IDs of the alerts to be updated and the values of the relevant fields that you wish to update for these alerts.</span></span>

<span data-ttu-id="87ca3-147">Предыдущие значения существующих свойств, не включенных в текст запроса, останутся прежними или будут повторно вычислены с учетом измененных значений других свойств.</span><span class="sxs-lookup"><span data-stu-id="87ca3-147">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span>

<span data-ttu-id="87ca3-148">Для достижения оптимальной производительности не следует включать существующие значения, которые не изменились.</span><span class="sxs-lookup"><span data-stu-id="87ca3-148">For best performance you shouldn't include existing values that haven't changed.</span></span>

<span data-ttu-id="87ca3-149">Свойство</span><span class="sxs-lookup"><span data-stu-id="87ca3-149">Property</span></span> | <span data-ttu-id="87ca3-150">Тип</span><span class="sxs-lookup"><span data-stu-id="87ca3-150">Type</span></span> | <span data-ttu-id="87ca3-151">Описание</span><span class="sxs-lookup"><span data-stu-id="87ca3-151">Description</span></span>
:---|:---|:---
<span data-ttu-id="87ca3-152">alertIds</span><span class="sxs-lookup"><span data-stu-id="87ca3-152">alertIds</span></span> | <span data-ttu-id="87ca3-153">Строка &lt; списка&gt;</span><span class="sxs-lookup"><span data-stu-id="87ca3-153">List&lt;String&gt;</span></span>| <span data-ttu-id="87ca3-154">Список ID-списков оповещений, которые необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="87ca3-154">A list of the IDs of the alerts to be updated.</span></span> <span data-ttu-id="87ca3-155">**Required**</span><span class="sxs-lookup"><span data-stu-id="87ca3-155">**Required**</span></span>
<span data-ttu-id="87ca3-156">status</span><span class="sxs-lookup"><span data-stu-id="87ca3-156">status</span></span> | <span data-ttu-id="87ca3-157">String</span><span class="sxs-lookup"><span data-stu-id="87ca3-157">String</span></span> | <span data-ttu-id="87ca3-158">Указывает обновленный статус указанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="87ca3-158">Specifies the updated status of the specified alerts.</span></span> <span data-ttu-id="87ca3-159">Значения свойств: "New", "InProgress" и "Resolved".</span><span class="sxs-lookup"><span data-stu-id="87ca3-159">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="87ca3-160">assignedTo</span><span class="sxs-lookup"><span data-stu-id="87ca3-160">assignedTo</span></span> | <span data-ttu-id="87ca3-161">String</span><span class="sxs-lookup"><span data-stu-id="87ca3-161">String</span></span> | <span data-ttu-id="87ca3-162">Владелец указанных оповещений</span><span class="sxs-lookup"><span data-stu-id="87ca3-162">Owner of the specified alerts</span></span>
<span data-ttu-id="87ca3-163">classification</span><span class="sxs-lookup"><span data-stu-id="87ca3-163">classification</span></span> | <span data-ttu-id="87ca3-164">String</span><span class="sxs-lookup"><span data-stu-id="87ca3-164">String</span></span> | <span data-ttu-id="87ca3-165">Указывает спецификацию указанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="87ca3-165">Specifies the specification of the specified alerts.</span></span> <span data-ttu-id="87ca3-166">Значения свойств: "Неизвестный", "FalsePositive", "TruePositive".</span><span class="sxs-lookup"><span data-stu-id="87ca3-166">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="87ca3-167">определение</span><span class="sxs-lookup"><span data-stu-id="87ca3-167">determination</span></span> | <span data-ttu-id="87ca3-168">Строка</span><span class="sxs-lookup"><span data-stu-id="87ca3-168">String</span></span> | <span data-ttu-id="87ca3-169">Указывает определение указанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="87ca3-169">Specifies the determination of the specified alerts.</span></span> <span data-ttu-id="87ca3-170">Значения свойств: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other"</span><span class="sxs-lookup"><span data-stu-id="87ca3-170">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="87ca3-171">comment</span><span class="sxs-lookup"><span data-stu-id="87ca3-171">comment</span></span> | <span data-ttu-id="87ca3-172">String</span><span class="sxs-lookup"><span data-stu-id="87ca3-172">String</span></span> | <span data-ttu-id="87ca3-173">Комментарий, который необходимо добавить в указанные оповещения.</span><span class="sxs-lookup"><span data-stu-id="87ca3-173">Comment to be added to the specified alerts.</span></span>

## <a name="response"></a><span data-ttu-id="87ca3-174">Отклик</span><span class="sxs-lookup"><span data-stu-id="87ca3-174">Response</span></span>

<span data-ttu-id="87ca3-175">В случае успешной работы этот метод возвращает 200 ОК с пустым телом отклика.</span><span class="sxs-lookup"><span data-stu-id="87ca3-175">If successful, this method returns 200 OK, with an empty response body.</span></span>

## <a name="example"></a><span data-ttu-id="87ca3-176">Пример</span><span class="sxs-lookup"><span data-stu-id="87ca3-176">Example</span></span>

### <a name="request"></a><span data-ttu-id="87ca3-177">Запрос</span><span class="sxs-lookup"><span data-stu-id="87ca3-177">Request</span></span>

<span data-ttu-id="87ca3-178">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="87ca3-178">Here is an example of the request.</span></span>

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
