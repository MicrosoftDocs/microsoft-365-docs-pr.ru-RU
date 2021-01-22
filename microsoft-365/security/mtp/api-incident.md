---
title: API инцидентов в Microsoft 365 Defender и тип ресурса инцидентов
description: Узнайте о методах и свойствах типа ресурса Incident в Microsoft 365 Defender
keywords: инцидент, инциденты, API
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928358"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="cb1ee-104">API инцидентов в Защитнике Microsoft 365 и тип ресурса инцидента</span><span class="sxs-lookup"><span data-stu-id="cb1ee-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cb1ee-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="cb1ee-105">**Applies to:**</span></span>

- <span data-ttu-id="cb1ee-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb1ee-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb1ee-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cb1ee-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="cb1ee-109">Инцидент [—](incidents-overview.md) это коллекция связанных оповещений, которые помогают описать атаку.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="cb1ee-110">События из разных организаций в организации автоматически объединяются Защитником Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="cb1ee-111">С помощью API инцидентов можно программным образом получать доступ к инцидентам и связанным оповещениям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="cb1ee-112">Квоты и выделение ресурсов</span><span class="sxs-lookup"><span data-stu-id="cb1ee-112">Quotas and resource allocation</span></span>

<span data-ttu-id="cb1ee-113">Можно запросить до 50 вызовов в минуту или 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="cb1ee-114">Каждый метод также имеет собственные квоты.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-114">Each method also has its own quotas.</span></span> <span data-ttu-id="cb1ee-115">Дополнительные сведения о квотах для конкретного метода см. в соответствующей статье о методе, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="cb1ee-116">Код http-ответа указывает, что вы достигли квоты по количеству отправленных запросов или по выделению `429` времени работы.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="cb1ee-117">Тело ответа будет включать время, пока квота не будет сброшена.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="cb1ee-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="cb1ee-118">Permissions</span></span>

<span data-ttu-id="cb1ee-119">API инцидентов требует различных типов разрешений для каждого из своих методов.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="cb1ee-120">Дополнительные сведения о необходимых разрешениях см. в статье соответствующего метода.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="cb1ee-121">Методы</span><span class="sxs-lookup"><span data-stu-id="cb1ee-121">Methods</span></span>

<span data-ttu-id="cb1ee-122">Метод</span><span class="sxs-lookup"><span data-stu-id="cb1ee-122">Method</span></span> | <span data-ttu-id="cb1ee-123">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="cb1ee-123">Return Type</span></span> | <span data-ttu-id="cb1ee-124">Описание</span><span class="sxs-lookup"><span data-stu-id="cb1ee-124">Description</span></span>
-|-|-
[<span data-ttu-id="cb1ee-125">Получение списка инцидентов</span><span class="sxs-lookup"><span data-stu-id="cb1ee-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="cb1ee-126">[Список инцидентов](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="cb1ee-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="cb1ee-127">Получите список инцидентов.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-127">Get a list of incidents.</span></span>
[<span data-ttu-id="cb1ee-128">Обновление данных об инциденте</span><span class="sxs-lookup"><span data-stu-id="cb1ee-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="cb1ee-129">Инцидент</span><span class="sxs-lookup"><span data-stu-id="cb1ee-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="cb1ee-130">Обновление определенного инцидента.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="cb1ee-131">Тело запроса, ответ и примеры</span><span class="sxs-lookup"><span data-stu-id="cb1ee-131">Request body, response, and examples</span></span>

<span data-ttu-id="cb1ee-132">Дополнительные сведения о том, как создать запрос или различенный ответ, а также практические примеры можно найти в соответствующих статьях о методе.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="cb1ee-133">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="cb1ee-133">Common properties</span></span>

<span data-ttu-id="cb1ee-134">Свойство</span><span class="sxs-lookup"><span data-stu-id="cb1ee-134">Property</span></span> | <span data-ttu-id="cb1ee-135">Тип</span><span class="sxs-lookup"><span data-stu-id="cb1ee-135">Type</span></span> | <span data-ttu-id="cb1ee-136">Описание</span><span class="sxs-lookup"><span data-stu-id="cb1ee-136">Description</span></span>
-|-|-
<span data-ttu-id="cb1ee-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="cb1ee-137">incidentId</span></span> | <span data-ttu-id="cb1ee-138">long</span><span class="sxs-lookup"><span data-stu-id="cb1ee-138">long</span></span> | <span data-ttu-id="cb1ee-139">Уникальный ИД инцидента.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-139">Incident unique ID.</span></span>
<span data-ttu-id="cb1ee-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="cb1ee-140">redirectIncidentId</span></span> | <span data-ttu-id="cb1ee-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="cb1ee-141">nullable long</span></span> | <span data-ttu-id="cb1ee-142">ИД инцидента, с который был объединен текущий инцидент.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="cb1ee-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="cb1ee-143">incidentName</span></span> | <span data-ttu-id="cb1ee-144">string</span><span class="sxs-lookup"><span data-stu-id="cb1ee-144">string</span></span> | <span data-ttu-id="cb1ee-145">Имя инцидента.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-145">The name of the Incident.</span></span>
<span data-ttu-id="cb1ee-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="cb1ee-146">createdTime</span></span> | <span data-ttu-id="cb1ee-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="cb1ee-147">DateTimeOffset</span></span> | <span data-ttu-id="cb1ee-148">Дата и время создания инцидента (в UTC).</span><span class="sxs-lookup"><span data-stu-id="cb1ee-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="cb1ee-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="cb1ee-149">lastUpdateTime</span></span> | <span data-ttu-id="cb1ee-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="cb1ee-150">DateTimeOffset</span></span> | <span data-ttu-id="cb1ee-151">Дата и время (в UTC) последнего обновления инцидента.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="cb1ee-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="cb1ee-152">assignedTo</span></span> | <span data-ttu-id="cb1ee-153">string</span><span class="sxs-lookup"><span data-stu-id="cb1ee-153">string</span></span> | <span data-ttu-id="cb1ee-154">Владелец инцидента.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-154">Owner of the Incident.</span></span>
<span data-ttu-id="cb1ee-155">severity</span><span class="sxs-lookup"><span data-stu-id="cb1ee-155">severity</span></span> | <span data-ttu-id="cb1ee-156">Перечисление</span><span class="sxs-lookup"><span data-stu-id="cb1ee-156">Enum</span></span> | <span data-ttu-id="cb1ee-157">Серьезность инцидента.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-157">Severity of the Incident.</span></span> <span data-ttu-id="cb1ee-158">Возможные значения: ```UnSpecified``` , , , , и ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="cb1ee-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="cb1ee-159">status</span><span class="sxs-lookup"><span data-stu-id="cb1ee-159">status</span></span> | <span data-ttu-id="cb1ee-160">Перечисление</span><span class="sxs-lookup"><span data-stu-id="cb1ee-160">Enum</span></span> | <span data-ttu-id="cb1ee-161">Указывает текущее состояние инцидента.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="cb1ee-162">Возможные значения: ```Active``` , , и ```Resolved``` ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="cb1ee-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="cb1ee-163">classification</span><span class="sxs-lookup"><span data-stu-id="cb1ee-163">classification</span></span> | <span data-ttu-id="cb1ee-164">Перечисление</span><span class="sxs-lookup"><span data-stu-id="cb1ee-164">Enum</span></span> | <span data-ttu-id="cb1ee-165">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-165">Specification of the incident.</span></span> <span data-ttu-id="cb1ee-166">Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="cb1ee-167">определение</span><span class="sxs-lookup"><span data-stu-id="cb1ee-167">determination</span></span> | <span data-ttu-id="cb1ee-168">Перечисление</span><span class="sxs-lookup"><span data-stu-id="cb1ee-168">Enum</span></span> | <span data-ttu-id="cb1ee-169">Определяет определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="cb1ee-170">Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="cb1ee-171">tags</span><span class="sxs-lookup"><span data-stu-id="cb1ee-171">tags</span></span> | <span data-ttu-id="cb1ee-172">string List</span><span class="sxs-lookup"><span data-stu-id="cb1ee-172">string List</span></span> | <span data-ttu-id="cb1ee-173">Список тегов инцидента.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-173">List of Incident tags.</span></span>
<span data-ttu-id="cb1ee-174">alerts</span><span class="sxs-lookup"><span data-stu-id="cb1ee-174">alerts</span></span> | <span data-ttu-id="cb1ee-175">Список оповещений</span><span class="sxs-lookup"><span data-stu-id="cb1ee-175">Alert List</span></span> | <span data-ttu-id="cb1ee-176">Список связанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-176">List of related alerts.</span></span> <span data-ttu-id="cb1ee-177">Примеры см. в документации по API [инцидентов](api-list-incidents.md) списка.</span><span class="sxs-lookup"><span data-stu-id="cb1ee-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cb1ee-178">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cb1ee-178">Related articles</span></span>

- [<span data-ttu-id="cb1ee-179">Обзор API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb1ee-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="cb1ee-180">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="cb1ee-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="cb1ee-181">API списка инцидентов</span><span class="sxs-lookup"><span data-stu-id="cb1ee-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="cb1ee-182">Обновление API инцидентов</span><span class="sxs-lookup"><span data-stu-id="cb1ee-182">Update incident API</span></span>](api-update-incidents.md)
