---
title: Microsoft 365 Инциденты с API-ресурсами защитника и тип ресурсов инцидента
description: Узнайте о методах и свойствах типа ресурса «Инцидент» в Microsoft 365 Defender
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
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572589"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="0994a-104">Microsoft 365 Api инцидентов защитника и тип ресурса инцидента</span><span class="sxs-lookup"><span data-stu-id="0994a-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0994a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0994a-105">**Applies to:**</span></span>

- <span data-ttu-id="0994a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0994a-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0994a-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="0994a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0994a-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="0994a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="0994a-109">Инцидент [представляет собой](incidents-overview.md) набор связанных оповещений, которые помогают описать атаку.</span><span class="sxs-lookup"><span data-stu-id="0994a-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="0994a-110">События из разных сущностей в вашей организации автоматически агрегируются Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="0994a-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="0994a-111">API инцидентов можно использовать для программного доступа к инцидентам и связанным с ними оповещениям организации.</span><span class="sxs-lookup"><span data-stu-id="0994a-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="0994a-112">Квоты и распределение ресурсов</span><span class="sxs-lookup"><span data-stu-id="0994a-112">Quotas and resource allocation</span></span>

<span data-ttu-id="0994a-113">Вы можете запросить до 50 звонков в минуту или 1500 звонков в час.</span><span class="sxs-lookup"><span data-stu-id="0994a-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="0994a-114">Каждый метод также имеет свои собственные квоты.</span><span class="sxs-lookup"><span data-stu-id="0994a-114">Each method also has its own quotas.</span></span> <span data-ttu-id="0994a-115">Для получения дополнительной информации о конкретных методах квот, см.</span><span class="sxs-lookup"><span data-stu-id="0994a-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="0994a-116">Код `429` ответа HTTP указывает на то, что вы достигли квоты либо по количеству отправленных запросов, либо по отведенному времени работы.</span><span class="sxs-lookup"><span data-stu-id="0994a-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="0994a-117">Орган реагирования будет включать время, пока квота, которую вы достигли, будет сброшена.</span><span class="sxs-lookup"><span data-stu-id="0994a-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="0994a-118">Разрешения</span><span class="sxs-lookup"><span data-stu-id="0994a-118">Permissions</span></span>

<span data-ttu-id="0994a-119">API инцидентов требует различных видов разрешений для каждого из своих методов.</span><span class="sxs-lookup"><span data-stu-id="0994a-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="0994a-120">Для получения дополнительной информации о необходимых разрешениях см.</span><span class="sxs-lookup"><span data-stu-id="0994a-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="0994a-121">Методы</span><span class="sxs-lookup"><span data-stu-id="0994a-121">Methods</span></span>

<span data-ttu-id="0994a-122">Метод</span><span class="sxs-lookup"><span data-stu-id="0994a-122">Method</span></span> | <span data-ttu-id="0994a-123">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="0994a-123">Return Type</span></span> | <span data-ttu-id="0994a-124">Описание</span><span class="sxs-lookup"><span data-stu-id="0994a-124">Description</span></span>
-|-|-
[<span data-ttu-id="0994a-125">Получение списка инцидентов</span><span class="sxs-lookup"><span data-stu-id="0994a-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="0994a-126">[Список инцидентов](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="0994a-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="0994a-127">Получить список инцидентов.</span><span class="sxs-lookup"><span data-stu-id="0994a-127">Get a list of incidents.</span></span>
[<span data-ttu-id="0994a-128">Обновление данных об инциденте</span><span class="sxs-lookup"><span data-stu-id="0994a-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="0994a-129">Инцидент</span><span class="sxs-lookup"><span data-stu-id="0994a-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="0994a-130">Обновление конкретного инцидента.</span><span class="sxs-lookup"><span data-stu-id="0994a-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="0994a-131">Орган запроса, ответ и примеры</span><span class="sxs-lookup"><span data-stu-id="0994a-131">Request body, response, and examples</span></span>

<span data-ttu-id="0994a-132">Для получения более подробной информации о том, как построить запрос или разобрать ответ, и для практических примеров обратитесь к соответствующим статьям метода.</span><span class="sxs-lookup"><span data-stu-id="0994a-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="0994a-133">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="0994a-133">Common properties</span></span>

<span data-ttu-id="0994a-134">Свойство</span><span class="sxs-lookup"><span data-stu-id="0994a-134">Property</span></span> | <span data-ttu-id="0994a-135">Тип</span><span class="sxs-lookup"><span data-stu-id="0994a-135">Type</span></span> | <span data-ttu-id="0994a-136">Описание</span><span class="sxs-lookup"><span data-stu-id="0994a-136">Description</span></span>
-|-|-
<span data-ttu-id="0994a-137">инцидентИд</span><span class="sxs-lookup"><span data-stu-id="0994a-137">incidentId</span></span> | <span data-ttu-id="0994a-138">long</span><span class="sxs-lookup"><span data-stu-id="0994a-138">long</span></span> | <span data-ttu-id="0994a-139">Инцидент уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="0994a-139">Incident unique ID.</span></span>
<span data-ttu-id="0994a-140">перенаправитьИдентид</span><span class="sxs-lookup"><span data-stu-id="0994a-140">redirectIncidentId</span></span> | <span data-ttu-id="0994a-141">нулевой долго</span><span class="sxs-lookup"><span data-stu-id="0994a-141">nullable long</span></span> | <span data-ttu-id="0994a-142">Идентификатор инцидента, к который был объединен текущий инцидент.</span><span class="sxs-lookup"><span data-stu-id="0994a-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="0994a-143">инцидентИмя</span><span class="sxs-lookup"><span data-stu-id="0994a-143">incidentName</span></span> | <span data-ttu-id="0994a-144">Строка</span><span class="sxs-lookup"><span data-stu-id="0994a-144">string</span></span> | <span data-ttu-id="0994a-145">Название Инцидента.</span><span class="sxs-lookup"><span data-stu-id="0994a-145">The name of the Incident.</span></span>
<span data-ttu-id="0994a-146">созданTime</span><span class="sxs-lookup"><span data-stu-id="0994a-146">createdTime</span></span> | <span data-ttu-id="0994a-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0994a-147">DateTimeOffset</span></span> | <span data-ttu-id="0994a-148">Дата и время (в UTC) Инцидент был создан.</span><span class="sxs-lookup"><span data-stu-id="0994a-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="0994a-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="0994a-149">lastUpdateTime</span></span> | <span data-ttu-id="0994a-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0994a-150">DateTimeOffset</span></span> | <span data-ttu-id="0994a-151">Дата и время (в UTC) Инцидент был в последний раз обновлен.</span><span class="sxs-lookup"><span data-stu-id="0994a-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="0994a-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="0994a-152">assignedTo</span></span> | <span data-ttu-id="0994a-153">Строка</span><span class="sxs-lookup"><span data-stu-id="0994a-153">string</span></span> | <span data-ttu-id="0994a-154">Владелец инцидента.</span><span class="sxs-lookup"><span data-stu-id="0994a-154">Owner of the Incident.</span></span>
<span data-ttu-id="0994a-155">severity</span><span class="sxs-lookup"><span data-stu-id="0994a-155">severity</span></span> | <span data-ttu-id="0994a-156">Перечисление</span><span class="sxs-lookup"><span data-stu-id="0994a-156">Enum</span></span> | <span data-ttu-id="0994a-157">Тяжесть инцидента.</span><span class="sxs-lookup"><span data-stu-id="0994a-157">Severity of the Incident.</span></span> <span data-ttu-id="0994a-158">Возможные значения: ```UnSpecified``` ```Informational``` , , , и ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="0994a-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="0994a-159">status</span><span class="sxs-lookup"><span data-stu-id="0994a-159">status</span></span> | <span data-ttu-id="0994a-160">Перечисление</span><span class="sxs-lookup"><span data-stu-id="0994a-160">Enum</span></span> | <span data-ttu-id="0994a-161">Уточняется текущее состояние происшествия.</span><span class="sxs-lookup"><span data-stu-id="0994a-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="0994a-162">Возможные значения: ```Active``` ```Resolved``` , и ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="0994a-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="0994a-163">classification</span><span class="sxs-lookup"><span data-stu-id="0994a-163">classification</span></span> | <span data-ttu-id="0994a-164">Перечисление</span><span class="sxs-lookup"><span data-stu-id="0994a-164">Enum</span></span> | <span data-ttu-id="0994a-165">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="0994a-165">Specification of the incident.</span></span> <span data-ttu-id="0994a-166">Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="0994a-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="0994a-167">решимость</span><span class="sxs-lookup"><span data-stu-id="0994a-167">determination</span></span> | <span data-ttu-id="0994a-168">Перечисление</span><span class="sxs-lookup"><span data-stu-id="0994a-168">Enum</span></span> | <span data-ttu-id="0994a-169">Уточняется определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="0994a-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="0994a-170">Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="0994a-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="0994a-171">tags</span><span class="sxs-lookup"><span data-stu-id="0994a-171">tags</span></span> | <span data-ttu-id="0994a-172">строка Список</span><span class="sxs-lookup"><span data-stu-id="0994a-172">string List</span></span> | <span data-ttu-id="0994a-173">Список тегов инцидента.</span><span class="sxs-lookup"><span data-stu-id="0994a-173">List of Incident tags.</span></span>
<span data-ttu-id="0994a-174">comments</span><span class="sxs-lookup"><span data-stu-id="0994a-174">comments</span></span> | <span data-ttu-id="0994a-175">Список комментариев по инцидентам</span><span class="sxs-lookup"><span data-stu-id="0994a-175">List of incident comments</span></span> | <span data-ttu-id="0994a-176">Объект Комментарий инцидента содержит: строку комментариев, созданную строкой и создать Время даты.</span><span class="sxs-lookup"><span data-stu-id="0994a-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="0994a-177">alerts</span><span class="sxs-lookup"><span data-stu-id="0994a-177">alerts</span></span> | <span data-ttu-id="0994a-178">Список оповещений</span><span class="sxs-lookup"><span data-stu-id="0994a-178">Alert List</span></span> | <span data-ttu-id="0994a-179">Список связанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="0994a-179">List of related alerts.</span></span> <span data-ttu-id="0994a-180">Смотрите примеры в [документации API по инцидентам](api-list-incidents.md) списка.</span><span class="sxs-lookup"><span data-stu-id="0994a-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0994a-181">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="0994a-181">Related articles</span></span>

- [<span data-ttu-id="0994a-182">Microsoft 365 Обзор API-и защитников</span><span class="sxs-lookup"><span data-stu-id="0994a-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="0994a-183">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="0994a-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="0994a-184">Список инцидентов API</span><span class="sxs-lookup"><span data-stu-id="0994a-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="0994a-185">Обновление API инцидента</span><span class="sxs-lookup"><span data-stu-id="0994a-185">Update incident API</span></span>](api-update-incidents.md)
