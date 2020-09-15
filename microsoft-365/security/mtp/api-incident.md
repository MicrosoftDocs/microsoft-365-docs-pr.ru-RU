---
title: Тип ресурса "инцидент" в API Microsoft Threat protection
description: Сведения о методах и свойствах типа ресурса инцидента в защите от угроз Майкрософт
keywords: инцидент, происшествия, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 310e3105c973223ea79373d770eb10f7753b917e
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650498"
---
# <a name="incident-resource-type"></a><span data-ttu-id="9a747-104">Тип ресурса инцидента</span><span class="sxs-lookup"><span data-stu-id="9a747-104">Incident resource type</span></span>

<span data-ttu-id="9a747-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9a747-105">**Applies to:**</span></span>
- <span data-ttu-id="9a747-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="9a747-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="9a747-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="9a747-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9a747-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="9a747-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="9a747-109">Методы</span><span class="sxs-lookup"><span data-stu-id="9a747-109">Methods</span></span>

<span data-ttu-id="9a747-110">Метод</span><span class="sxs-lookup"><span data-stu-id="9a747-110">Method</span></span> |<span data-ttu-id="9a747-111">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="9a747-111">Return Type</span></span> |<span data-ttu-id="9a747-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9a747-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="9a747-113">Список инцидентов</span><span class="sxs-lookup"><span data-stu-id="9a747-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="9a747-114">Список [инцидентов](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="9a747-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="9a747-115">Получение списка инцидентов.</span><span class="sxs-lookup"><span data-stu-id="9a747-115">Get a list of incidents.</span></span>
[<span data-ttu-id="9a747-116">Обновление инцидента</span><span class="sxs-lookup"><span data-stu-id="9a747-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="9a747-117">Случаях</span><span class="sxs-lookup"><span data-stu-id="9a747-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="9a747-118">Обновление конкретного инцидента.</span><span class="sxs-lookup"><span data-stu-id="9a747-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="9a747-119">Свойства</span><span class="sxs-lookup"><span data-stu-id="9a747-119">Properties</span></span>

<span data-ttu-id="9a747-120">Свойство</span><span class="sxs-lookup"><span data-stu-id="9a747-120">Property</span></span> |    <span data-ttu-id="9a747-121">Тип</span><span class="sxs-lookup"><span data-stu-id="9a747-121">Type</span></span>    |    <span data-ttu-id="9a747-122">Описание</span><span class="sxs-lookup"><span data-stu-id="9a747-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="9a747-123">инЦидентид</span><span class="sxs-lookup"><span data-stu-id="9a747-123">incidentId</span></span> | <span data-ttu-id="9a747-124">long</span><span class="sxs-lookup"><span data-stu-id="9a747-124">long</span></span> | <span data-ttu-id="9a747-125">Уникальный идентификатор инцидента.</span><span class="sxs-lookup"><span data-stu-id="9a747-125">Incident unique ID.</span></span>
<span data-ttu-id="9a747-126">редиректинЦидентид</span><span class="sxs-lookup"><span data-stu-id="9a747-126">redirectIncidentId</span></span> | <span data-ttu-id="9a747-127">Long, допускающий значение null</span><span class="sxs-lookup"><span data-stu-id="9a747-127">nullable long</span></span> | <span data-ttu-id="9a747-128">Идентификатор инцидента, с которым было выполнено слияние текущего инцидента.</span><span class="sxs-lookup"><span data-stu-id="9a747-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="9a747-129">инЦидентнаме</span><span class="sxs-lookup"><span data-stu-id="9a747-129">incidentName</span></span> | <span data-ttu-id="9a747-130">string</span><span class="sxs-lookup"><span data-stu-id="9a747-130">string</span></span> | <span data-ttu-id="9a747-131">Имя инцидента.</span><span class="sxs-lookup"><span data-stu-id="9a747-131">The name of the Incident.</span></span>
<span data-ttu-id="9a747-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="9a747-132">createdTime</span></span> | <span data-ttu-id="9a747-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="9a747-133">DateTimeOffset</span></span> | <span data-ttu-id="9a747-134">Дата и время создания инцидента (в формате UTC).</span><span class="sxs-lookup"><span data-stu-id="9a747-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="9a747-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="9a747-135">lastUpdateTime</span></span> | <span data-ttu-id="9a747-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="9a747-136">DateTimeOffset</span></span> | <span data-ttu-id="9a747-137">Дата и время последнего обновления инцидента (в формате UTC).</span><span class="sxs-lookup"><span data-stu-id="9a747-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="9a747-138">assignedTo</span><span class="sxs-lookup"><span data-stu-id="9a747-138">assignedTo</span></span> | <span data-ttu-id="9a747-139">string</span><span class="sxs-lookup"><span data-stu-id="9a747-139">string</span></span> | <span data-ttu-id="9a747-140">Владелец инцидента.</span><span class="sxs-lookup"><span data-stu-id="9a747-140">Owner of the Incident.</span></span>
<span data-ttu-id="9a747-141">severity</span><span class="sxs-lookup"><span data-stu-id="9a747-141">severity</span></span> | <span data-ttu-id="9a747-142">Перечисление</span><span class="sxs-lookup"><span data-stu-id="9a747-142">Enum</span></span> | <span data-ttu-id="9a747-143">Степень серьезности инцидента.</span><span class="sxs-lookup"><span data-stu-id="9a747-143">Severity of the Incident.</span></span> <span data-ttu-id="9a747-144">Возможные значения: ```UnSpecified``` , ```Informational``` , ```Low``` ```Medium``` и ```High``` .</span><span class="sxs-lookup"><span data-stu-id="9a747-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="9a747-145">status</span><span class="sxs-lookup"><span data-stu-id="9a747-145">status</span></span> | <span data-ttu-id="9a747-146">Перечисление</span><span class="sxs-lookup"><span data-stu-id="9a747-146">Enum</span></span> | <span data-ttu-id="9a747-147">Указывает текущее состояние инцидента.</span><span class="sxs-lookup"><span data-stu-id="9a747-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="9a747-148">Возможные значения: ```Active``` ```Resolved``` и ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="9a747-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="9a747-149">classification</span><span class="sxs-lookup"><span data-stu-id="9a747-149">classification</span></span> | <span data-ttu-id="9a747-150">Перечисление</span><span class="sxs-lookup"><span data-stu-id="9a747-150">Enum</span></span> | <span data-ttu-id="9a747-151">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="9a747-151">Specification of the incident.</span></span> <span data-ttu-id="9a747-152">Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="9a747-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="9a747-153">решение</span><span class="sxs-lookup"><span data-stu-id="9a747-153">determination</span></span> | <span data-ttu-id="9a747-154">Перечисление</span><span class="sxs-lookup"><span data-stu-id="9a747-154">Enum</span></span> | <span data-ttu-id="9a747-155">Указывает на определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="9a747-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="9a747-156">Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="9a747-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="9a747-157">tags</span><span class="sxs-lookup"><span data-stu-id="9a747-157">tags</span></span> | <span data-ttu-id="9a747-158">Список строк</span><span class="sxs-lookup"><span data-stu-id="9a747-158">string List</span></span> | <span data-ttu-id="9a747-159">Список тегов инцидента.</span><span class="sxs-lookup"><span data-stu-id="9a747-159">List of Incident tags.</span></span>
<span data-ttu-id="9a747-160">alerts</span><span class="sxs-lookup"><span data-stu-id="9a747-160">alerts</span></span> | <span data-ttu-id="9a747-161">Список оповещений</span><span class="sxs-lookup"><span data-stu-id="9a747-161">Alert List</span></span> | <span data-ttu-id="9a747-162">Список связанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="9a747-162">List of related alerts.</span></span> <span data-ttu-id="9a747-163">В этой статье приведены примеры документации по API [происшествий](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="9a747-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>