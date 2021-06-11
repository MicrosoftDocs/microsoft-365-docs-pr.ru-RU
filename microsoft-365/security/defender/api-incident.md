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
ms.openlocfilehash: 0c0c2e280f63076687a0854e25c47577b050a8f7
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888437"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="4ba9d-104">Microsoft 365 API инцидентов Defender и тип ресурса инцидентов</span><span class="sxs-lookup"><span data-stu-id="4ba9d-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4ba9d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4ba9d-105">**Applies to:**</span></span>

- [<span data-ttu-id="4ba9d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ba9d-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="4ba9d-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="4ba9d-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="4ba9d-109">Инцидент [—](incidents-overview.md) это набор связанных оповещений, которые помогают описать атаку.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="4ba9d-110">События из разных сущностями в вашей организации автоматически агрегируются Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="4ba9d-111">API инцидентов можно использовать для программного доступа к инцидентам и связанным оповещениям организации.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="4ba9d-112">Квоты и распределение ресурсов</span><span class="sxs-lookup"><span data-stu-id="4ba9d-112">Quotas and resource allocation</span></span>

<span data-ttu-id="4ba9d-113">Вы можете запрашивать до 50 вызовов в минуту или 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="4ba9d-114">Каждый метод также имеет свои квоты.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-114">Each method also has its own quotas.</span></span> <span data-ttu-id="4ba9d-115">Дополнительные сведения о квотах, определенных методом, см. в соответствующей статье для метода, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="4ba9d-116">Код ответа HTTP указывает, что вы достигли квоты либо по количеству отправленных запросов, либо по `429` выделенной продолжительной работе.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="4ba9d-117">В органе ответа будет включено время, пока квота, которая была достигнута, не будет сброшена.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="4ba9d-118">Разрешения</span><span class="sxs-lookup"><span data-stu-id="4ba9d-118">Permissions</span></span>

<span data-ttu-id="4ba9d-119">API инцидентов требует различных разрешений для каждого из его методов.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="4ba9d-120">Дополнительные сведения о необходимых разрешениях см. в статье соответствующего метода.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="4ba9d-121">Методы</span><span class="sxs-lookup"><span data-stu-id="4ba9d-121">Methods</span></span>

<span data-ttu-id="4ba9d-122">Метод</span><span class="sxs-lookup"><span data-stu-id="4ba9d-122">Method</span></span> | <span data-ttu-id="4ba9d-123">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="4ba9d-123">Return Type</span></span> | <span data-ttu-id="4ba9d-124">Описание</span><span class="sxs-lookup"><span data-stu-id="4ba9d-124">Description</span></span>
-|-|-
[<span data-ttu-id="4ba9d-125">Получение списка инцидентов</span><span class="sxs-lookup"><span data-stu-id="4ba9d-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="4ba9d-126">[Список инцидентов](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="4ba9d-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="4ba9d-127">Получите список инцидентов.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-127">Get a list of incidents.</span></span>
[<span data-ttu-id="4ba9d-128">Обновление данных об инциденте</span><span class="sxs-lookup"><span data-stu-id="4ba9d-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="4ba9d-129">Инцидент</span><span class="sxs-lookup"><span data-stu-id="4ba9d-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="4ba9d-130">Обновление определенного инцидента.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-130">Update a specific incident.</span></span>
[<span data-ttu-id="4ba9d-131">Получить инцидент</span><span class="sxs-lookup"><span data-stu-id="4ba9d-131">Get incident</span></span>](api-get-incident.md) | [<span data-ttu-id="4ba9d-132">Инцидент</span><span class="sxs-lookup"><span data-stu-id="4ba9d-132">Incident</span></span>](api-incident.md) | <span data-ttu-id="4ba9d-133">Получите один инцидент.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-133">Get a single incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="4ba9d-134">Запрос тела, ответа и примеров</span><span class="sxs-lookup"><span data-stu-id="4ba9d-134">Request body, response, and examples</span></span>

<span data-ttu-id="4ba9d-135">Дополнительные сведения о том, как создать запрос или размыть ответ, а также практические примеры.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-135">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="4ba9d-136">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="4ba9d-136">Common properties</span></span>

<span data-ttu-id="4ba9d-137">Свойство</span><span class="sxs-lookup"><span data-stu-id="4ba9d-137">Property</span></span> | <span data-ttu-id="4ba9d-138">Тип</span><span class="sxs-lookup"><span data-stu-id="4ba9d-138">Type</span></span> | <span data-ttu-id="4ba9d-139">Описание</span><span class="sxs-lookup"><span data-stu-id="4ba9d-139">Description</span></span>
-|-|-
<span data-ttu-id="4ba9d-140">incidentId</span><span class="sxs-lookup"><span data-stu-id="4ba9d-140">incidentId</span></span> | <span data-ttu-id="4ba9d-141">long</span><span class="sxs-lookup"><span data-stu-id="4ba9d-141">long</span></span> | <span data-ttu-id="4ba9d-142">Уникальный ID инцидента.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-142">Incident unique ID.</span></span>
<span data-ttu-id="4ba9d-143">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="4ba9d-143">redirectIncidentId</span></span> | <span data-ttu-id="4ba9d-144">nullable long</span><span class="sxs-lookup"><span data-stu-id="4ba9d-144">nullable long</span></span> | <span data-ttu-id="4ba9d-145">ID инцидента, в который был объединено текущее происшествие.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-145">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="4ba9d-146">incidentName</span><span class="sxs-lookup"><span data-stu-id="4ba9d-146">incidentName</span></span> | <span data-ttu-id="4ba9d-147">string</span><span class="sxs-lookup"><span data-stu-id="4ba9d-147">string</span></span> | <span data-ttu-id="4ba9d-148">Имя инцидента.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-148">The name of the Incident.</span></span>
<span data-ttu-id="4ba9d-149">createdTime</span><span class="sxs-lookup"><span data-stu-id="4ba9d-149">createdTime</span></span> | <span data-ttu-id="4ba9d-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="4ba9d-150">DateTimeOffset</span></span> | <span data-ttu-id="4ba9d-151">Дата и время (в UTC) был создан инцидент.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-151">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="4ba9d-152">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="4ba9d-152">lastUpdateTime</span></span> | <span data-ttu-id="4ba9d-153">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="4ba9d-153">DateTimeOffset</span></span> | <span data-ttu-id="4ba9d-154">Дата и время (в UTC) инцидент был последним обновлением.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-154">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="4ba9d-155">assignedTo</span><span class="sxs-lookup"><span data-stu-id="4ba9d-155">assignedTo</span></span> | <span data-ttu-id="4ba9d-156">string</span><span class="sxs-lookup"><span data-stu-id="4ba9d-156">string</span></span> | <span data-ttu-id="4ba9d-157">Владелец инцидента.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-157">Owner of the Incident.</span></span>
<span data-ttu-id="4ba9d-158">severity</span><span class="sxs-lookup"><span data-stu-id="4ba9d-158">severity</span></span> | <span data-ttu-id="4ba9d-159">Перечисление</span><span class="sxs-lookup"><span data-stu-id="4ba9d-159">Enum</span></span> | <span data-ttu-id="4ba9d-160">Серьезность инцидента.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-160">Severity of the Incident.</span></span> <span data-ttu-id="4ba9d-161">Возможные значения: ```UnSpecified``` ```Informational``` , , , , ```Low``` и ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="4ba9d-161">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="4ba9d-162">status</span><span class="sxs-lookup"><span data-stu-id="4ba9d-162">status</span></span> | <span data-ttu-id="4ba9d-163">Перечисление</span><span class="sxs-lookup"><span data-stu-id="4ba9d-163">Enum</span></span> | <span data-ttu-id="4ba9d-164">Указывает текущее состояние инцидента.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-164">Specifies the current status of the incident.</span></span> <span data-ttu-id="4ba9d-165">Возможные значения: ```Active``` , ```Resolved``` и ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="4ba9d-165">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="4ba9d-166">classification</span><span class="sxs-lookup"><span data-stu-id="4ba9d-166">classification</span></span> | <span data-ttu-id="4ba9d-167">Перечисление</span><span class="sxs-lookup"><span data-stu-id="4ba9d-167">Enum</span></span> | <span data-ttu-id="4ba9d-168">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-168">Specification of the incident.</span></span> <span data-ttu-id="4ba9d-169">Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-169">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="4ba9d-170">определение</span><span class="sxs-lookup"><span data-stu-id="4ba9d-170">determination</span></span> | <span data-ttu-id="4ba9d-171">Перечисление</span><span class="sxs-lookup"><span data-stu-id="4ba9d-171">Enum</span></span> | <span data-ttu-id="4ba9d-172">Указывает определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-172">Specifies the determination of the incident.</span></span> <span data-ttu-id="4ba9d-173">Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-173">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="4ba9d-174">tags</span><span class="sxs-lookup"><span data-stu-id="4ba9d-174">tags</span></span> | <span data-ttu-id="4ba9d-175">строка Список</span><span class="sxs-lookup"><span data-stu-id="4ba9d-175">string List</span></span> | <span data-ttu-id="4ba9d-176">Список тегов Инцидент.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-176">List of Incident tags.</span></span>
<span data-ttu-id="4ba9d-177">comments</span><span class="sxs-lookup"><span data-stu-id="4ba9d-177">comments</span></span> | <span data-ttu-id="4ba9d-178">Список комментариев об инцидентах</span><span class="sxs-lookup"><span data-stu-id="4ba9d-178">List of incident comments</span></span> | <span data-ttu-id="4ba9d-179">Объект Комментарий инцидента содержит строку комментариев, созданную строкуBy и время даты созданияTime.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-179">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="4ba9d-180">alerts</span><span class="sxs-lookup"><span data-stu-id="4ba9d-180">alerts</span></span> | <span data-ttu-id="4ba9d-181">Список оповещений</span><span class="sxs-lookup"><span data-stu-id="4ba9d-181">Alert List</span></span> | <span data-ttu-id="4ba9d-182">Список связанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-182">List of related alerts.</span></span> <span data-ttu-id="4ba9d-183">Примеры см. в [документации API инцидентов](api-list-incidents.md) списка.</span><span class="sxs-lookup"><span data-stu-id="4ba9d-183">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4ba9d-184">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="4ba9d-184">Related articles</span></span>

- [<span data-ttu-id="4ba9d-185">Microsoft 365 Обзор API defender</span><span class="sxs-lookup"><span data-stu-id="4ba9d-185">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="4ba9d-186">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="4ba9d-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="4ba9d-187">API инцидентов списка</span><span class="sxs-lookup"><span data-stu-id="4ba9d-187">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="4ba9d-188">Обновление API инцидента</span><span class="sxs-lookup"><span data-stu-id="4ba9d-188">Update incident API</span></span>](api-update-incidents.md)
