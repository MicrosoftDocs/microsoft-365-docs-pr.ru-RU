---
title: Microsoft 365 Defender incidents API and the incidents resource type
description: Узнайте о методах и свойствах типа ресурсов Incidents в Microsoft 365 Defender
keywords: инциденты, инциденты, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 587d6107b0c09b2178311d8da6606968e7fda083
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730934"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="19caf-104">Microsoft 365 API инцидентов Defender и тип ресурса инцидентов</span><span class="sxs-lookup"><span data-stu-id="19caf-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="19caf-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="19caf-105">**Applies to:**</span></span>

- [<span data-ttu-id="19caf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19caf-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="19caf-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="19caf-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="19caf-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="19caf-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="19caf-109">Инцидент [—](incidents-overview.md) это набор связанных оповещений, которые помогают описать атаку.</span><span class="sxs-lookup"><span data-stu-id="19caf-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="19caf-110">События из разных сущностями в вашей организации автоматически агрегируются Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="19caf-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="19caf-111">API инцидентов можно использовать для программного доступа к инцидентам и связанным оповещениям организации.</span><span class="sxs-lookup"><span data-stu-id="19caf-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="19caf-112">Квоты и распределение ресурсов</span><span class="sxs-lookup"><span data-stu-id="19caf-112">Quotas and resource allocation</span></span>

<span data-ttu-id="19caf-113">Вы можете запрашивать до 50 вызовов в минуту или 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="19caf-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="19caf-114">Каждый метод также имеет свои квоты.</span><span class="sxs-lookup"><span data-stu-id="19caf-114">Each method also has its own quotas.</span></span> <span data-ttu-id="19caf-115">Дополнительные сведения о квотах, определенных методом, см. в соответствующей статье для метода, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="19caf-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="19caf-116">Код ответа HTTP указывает, что вы достигли квоты либо по количеству отправленных запросов, либо по `429` выделенной продолжительной работе.</span><span class="sxs-lookup"><span data-stu-id="19caf-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="19caf-117">В органе ответа будет включено время, пока квота, которая была достигнута, не будет сброшена.</span><span class="sxs-lookup"><span data-stu-id="19caf-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="19caf-118">Разрешения</span><span class="sxs-lookup"><span data-stu-id="19caf-118">Permissions</span></span>

<span data-ttu-id="19caf-119">API инцидентов требует различных разрешений для каждого из его методов.</span><span class="sxs-lookup"><span data-stu-id="19caf-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="19caf-120">Дополнительные сведения о необходимых разрешениях см. в статье соответствующего метода.</span><span class="sxs-lookup"><span data-stu-id="19caf-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="19caf-121">Методы</span><span class="sxs-lookup"><span data-stu-id="19caf-121">Methods</span></span>

<span data-ttu-id="19caf-122">Метод</span><span class="sxs-lookup"><span data-stu-id="19caf-122">Method</span></span> | <span data-ttu-id="19caf-123">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="19caf-123">Return Type</span></span> | <span data-ttu-id="19caf-124">Описание</span><span class="sxs-lookup"><span data-stu-id="19caf-124">Description</span></span>
-|-|-
[<span data-ttu-id="19caf-125">Получение списка инцидентов</span><span class="sxs-lookup"><span data-stu-id="19caf-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="19caf-126">[Список инцидентов](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="19caf-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="19caf-127">Получите список инцидентов.</span><span class="sxs-lookup"><span data-stu-id="19caf-127">Get a list of incidents.</span></span>
[<span data-ttu-id="19caf-128">Обновление данных об инциденте</span><span class="sxs-lookup"><span data-stu-id="19caf-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="19caf-129">Инцидент</span><span class="sxs-lookup"><span data-stu-id="19caf-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="19caf-130">Обновление определенного инцидента.</span><span class="sxs-lookup"><span data-stu-id="19caf-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="19caf-131">Запрос тела, ответа и примеров</span><span class="sxs-lookup"><span data-stu-id="19caf-131">Request body, response, and examples</span></span>

<span data-ttu-id="19caf-132">Дополнительные сведения о том, как создать запрос или размыть ответ, а также практические примеры.</span><span class="sxs-lookup"><span data-stu-id="19caf-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="19caf-133">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="19caf-133">Common properties</span></span>

<span data-ttu-id="19caf-134">Свойство</span><span class="sxs-lookup"><span data-stu-id="19caf-134">Property</span></span> | <span data-ttu-id="19caf-135">Тип</span><span class="sxs-lookup"><span data-stu-id="19caf-135">Type</span></span> | <span data-ttu-id="19caf-136">Описание</span><span class="sxs-lookup"><span data-stu-id="19caf-136">Description</span></span>
-|-|-
<span data-ttu-id="19caf-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="19caf-137">incidentId</span></span> | <span data-ttu-id="19caf-138">long</span><span class="sxs-lookup"><span data-stu-id="19caf-138">long</span></span> | <span data-ttu-id="19caf-139">Уникальный ID инцидента.</span><span class="sxs-lookup"><span data-stu-id="19caf-139">Incident unique ID.</span></span>
<span data-ttu-id="19caf-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="19caf-140">redirectIncidentId</span></span> | <span data-ttu-id="19caf-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="19caf-141">nullable long</span></span> | <span data-ttu-id="19caf-142">ID инцидента, в который был объединено текущее происшествие.</span><span class="sxs-lookup"><span data-stu-id="19caf-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="19caf-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="19caf-143">incidentName</span></span> | <span data-ttu-id="19caf-144">Строка</span><span class="sxs-lookup"><span data-stu-id="19caf-144">string</span></span> | <span data-ttu-id="19caf-145">Имя инцидента.</span><span class="sxs-lookup"><span data-stu-id="19caf-145">The name of the Incident.</span></span>
<span data-ttu-id="19caf-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="19caf-146">createdTime</span></span> | <span data-ttu-id="19caf-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="19caf-147">DateTimeOffset</span></span> | <span data-ttu-id="19caf-148">Дата и время (в UTC) был создан инцидент.</span><span class="sxs-lookup"><span data-stu-id="19caf-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="19caf-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="19caf-149">lastUpdateTime</span></span> | <span data-ttu-id="19caf-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="19caf-150">DateTimeOffset</span></span> | <span data-ttu-id="19caf-151">Дата и время (в UTC) инцидент был последним обновлением.</span><span class="sxs-lookup"><span data-stu-id="19caf-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="19caf-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="19caf-152">assignedTo</span></span> | <span data-ttu-id="19caf-153">Строка</span><span class="sxs-lookup"><span data-stu-id="19caf-153">string</span></span> | <span data-ttu-id="19caf-154">Владелец инцидента.</span><span class="sxs-lookup"><span data-stu-id="19caf-154">Owner of the Incident.</span></span>
<span data-ttu-id="19caf-155">severity</span><span class="sxs-lookup"><span data-stu-id="19caf-155">severity</span></span> | <span data-ttu-id="19caf-156">Перечисление</span><span class="sxs-lookup"><span data-stu-id="19caf-156">Enum</span></span> | <span data-ttu-id="19caf-157">Серьезность инцидента.</span><span class="sxs-lookup"><span data-stu-id="19caf-157">Severity of the Incident.</span></span> <span data-ttu-id="19caf-158">Возможные значения: ```UnSpecified``` ```Informational``` , , , , ```Low``` и ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="19caf-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="19caf-159">status</span><span class="sxs-lookup"><span data-stu-id="19caf-159">status</span></span> | <span data-ttu-id="19caf-160">Перечисление</span><span class="sxs-lookup"><span data-stu-id="19caf-160">Enum</span></span> | <span data-ttu-id="19caf-161">Указывает текущее состояние инцидента.</span><span class="sxs-lookup"><span data-stu-id="19caf-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="19caf-162">Возможные значения: ```Active``` , ```Resolved``` и ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="19caf-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="19caf-163">classification</span><span class="sxs-lookup"><span data-stu-id="19caf-163">classification</span></span> | <span data-ttu-id="19caf-164">Перечисление</span><span class="sxs-lookup"><span data-stu-id="19caf-164">Enum</span></span> | <span data-ttu-id="19caf-165">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="19caf-165">Specification of the incident.</span></span> <span data-ttu-id="19caf-166">Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="19caf-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="19caf-167">определение</span><span class="sxs-lookup"><span data-stu-id="19caf-167">determination</span></span> | <span data-ttu-id="19caf-168">Перечисление</span><span class="sxs-lookup"><span data-stu-id="19caf-168">Enum</span></span> | <span data-ttu-id="19caf-169">Указывает определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="19caf-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="19caf-170">Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="19caf-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="19caf-171">tags</span><span class="sxs-lookup"><span data-stu-id="19caf-171">tags</span></span> | <span data-ttu-id="19caf-172">строка Список</span><span class="sxs-lookup"><span data-stu-id="19caf-172">string List</span></span> | <span data-ttu-id="19caf-173">Список тегов Инцидент.</span><span class="sxs-lookup"><span data-stu-id="19caf-173">List of Incident tags.</span></span>
<span data-ttu-id="19caf-174">comments</span><span class="sxs-lookup"><span data-stu-id="19caf-174">comments</span></span> | <span data-ttu-id="19caf-175">Список комментариев об инцидентах</span><span class="sxs-lookup"><span data-stu-id="19caf-175">List of incident comments</span></span> | <span data-ttu-id="19caf-176">Объект Комментарий инцидента содержит строку комментариев, созданную строкуBy и время даты созданияTime.</span><span class="sxs-lookup"><span data-stu-id="19caf-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="19caf-177">alerts</span><span class="sxs-lookup"><span data-stu-id="19caf-177">alerts</span></span> | <span data-ttu-id="19caf-178">Список оповещений</span><span class="sxs-lookup"><span data-stu-id="19caf-178">Alert List</span></span> | <span data-ttu-id="19caf-179">Список связанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="19caf-179">List of related alerts.</span></span> <span data-ttu-id="19caf-180">Примеры см. в [документации API инцидентов](api-list-incidents.md) списка.</span><span class="sxs-lookup"><span data-stu-id="19caf-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="19caf-181">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="19caf-181">Related articles</span></span>

- [<span data-ttu-id="19caf-182">Microsoft 365 Обзор API defender</span><span class="sxs-lookup"><span data-stu-id="19caf-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="19caf-183">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="19caf-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="19caf-184">API инцидентов списка</span><span class="sxs-lookup"><span data-stu-id="19caf-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="19caf-185">Обновление API инцидента</span><span class="sxs-lookup"><span data-stu-id="19caf-185">Update incident API</span></span>](api-update-incidents.md)
