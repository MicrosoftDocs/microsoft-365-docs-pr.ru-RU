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
ms.openlocfilehash: ac149ca7263b8ef8bb37a7dd18bf0787a3114b37
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201307"
---
# <a name="incident-resource-type"></a><span data-ttu-id="1226b-104">Тип ресурса инцидента</span><span class="sxs-lookup"><span data-stu-id="1226b-104">Incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1226b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1226b-105">**Applies to:**</span></span>
- <span data-ttu-id="1226b-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1226b-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="1226b-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="1226b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1226b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="1226b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="1226b-109">Методы</span><span class="sxs-lookup"><span data-stu-id="1226b-109">Methods</span></span>

<span data-ttu-id="1226b-110">Метод</span><span class="sxs-lookup"><span data-stu-id="1226b-110">Method</span></span> |<span data-ttu-id="1226b-111">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="1226b-111">Return Type</span></span> |<span data-ttu-id="1226b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1226b-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="1226b-113">Получение списка инцидентов</span><span class="sxs-lookup"><span data-stu-id="1226b-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="1226b-114">Список [инцидентов](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="1226b-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="1226b-115">Получение списка инцидентов.</span><span class="sxs-lookup"><span data-stu-id="1226b-115">Get a list of incidents.</span></span>
[<span data-ttu-id="1226b-116">Обновление данных об инциденте</span><span class="sxs-lookup"><span data-stu-id="1226b-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="1226b-117">Случаях</span><span class="sxs-lookup"><span data-stu-id="1226b-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="1226b-118">Обновление конкретного инцидента.</span><span class="sxs-lookup"><span data-stu-id="1226b-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="1226b-119">Свойства</span><span class="sxs-lookup"><span data-stu-id="1226b-119">Properties</span></span>

<span data-ttu-id="1226b-120">Свойство</span><span class="sxs-lookup"><span data-stu-id="1226b-120">Property</span></span> |    <span data-ttu-id="1226b-121">Тип</span><span class="sxs-lookup"><span data-stu-id="1226b-121">Type</span></span>    |    <span data-ttu-id="1226b-122">Описание</span><span class="sxs-lookup"><span data-stu-id="1226b-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="1226b-123">инЦидентид</span><span class="sxs-lookup"><span data-stu-id="1226b-123">incidentId</span></span> | <span data-ttu-id="1226b-124">long</span><span class="sxs-lookup"><span data-stu-id="1226b-124">long</span></span> | <span data-ttu-id="1226b-125">Уникальный идентификатор инцидента.</span><span class="sxs-lookup"><span data-stu-id="1226b-125">Incident unique ID.</span></span>
<span data-ttu-id="1226b-126">редиректинЦидентид</span><span class="sxs-lookup"><span data-stu-id="1226b-126">redirectIncidentId</span></span> | <span data-ttu-id="1226b-127">Long, допускающий значение null</span><span class="sxs-lookup"><span data-stu-id="1226b-127">nullable long</span></span> | <span data-ttu-id="1226b-128">Идентификатор инцидента, с которым было выполнено слияние текущего инцидента.</span><span class="sxs-lookup"><span data-stu-id="1226b-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="1226b-129">инЦидентнаме</span><span class="sxs-lookup"><span data-stu-id="1226b-129">incidentName</span></span> | <span data-ttu-id="1226b-130">string</span><span class="sxs-lookup"><span data-stu-id="1226b-130">string</span></span> | <span data-ttu-id="1226b-131">Имя инцидента.</span><span class="sxs-lookup"><span data-stu-id="1226b-131">The name of the Incident.</span></span>
<span data-ttu-id="1226b-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="1226b-132">createdTime</span></span> | <span data-ttu-id="1226b-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1226b-133">DateTimeOffset</span></span> | <span data-ttu-id="1226b-134">Дата и время создания инцидента (в формате UTC).</span><span class="sxs-lookup"><span data-stu-id="1226b-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="1226b-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="1226b-135">lastUpdateTime</span></span> | <span data-ttu-id="1226b-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1226b-136">DateTimeOffset</span></span> | <span data-ttu-id="1226b-137">Дата и время последнего обновления инцидента (в формате UTC).</span><span class="sxs-lookup"><span data-stu-id="1226b-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="1226b-138">assignedTo</span><span class="sxs-lookup"><span data-stu-id="1226b-138">assignedTo</span></span> | <span data-ttu-id="1226b-139">string</span><span class="sxs-lookup"><span data-stu-id="1226b-139">string</span></span> | <span data-ttu-id="1226b-140">Владелец инцидента.</span><span class="sxs-lookup"><span data-stu-id="1226b-140">Owner of the Incident.</span></span>
<span data-ttu-id="1226b-141">severity</span><span class="sxs-lookup"><span data-stu-id="1226b-141">severity</span></span> | <span data-ttu-id="1226b-142">Перечисление</span><span class="sxs-lookup"><span data-stu-id="1226b-142">Enum</span></span> | <span data-ttu-id="1226b-143">Степень серьезности инцидента.</span><span class="sxs-lookup"><span data-stu-id="1226b-143">Severity of the Incident.</span></span> <span data-ttu-id="1226b-144">Возможные значения: ```UnSpecified``` , ```Informational``` , ```Low``` ```Medium``` и ```High``` .</span><span class="sxs-lookup"><span data-stu-id="1226b-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="1226b-145">status</span><span class="sxs-lookup"><span data-stu-id="1226b-145">status</span></span> | <span data-ttu-id="1226b-146">Перечисление</span><span class="sxs-lookup"><span data-stu-id="1226b-146">Enum</span></span> | <span data-ttu-id="1226b-147">Указывает текущее состояние инцидента.</span><span class="sxs-lookup"><span data-stu-id="1226b-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="1226b-148">Возможные значения: ```Active``` ```Resolved``` и ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="1226b-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="1226b-149">classification</span><span class="sxs-lookup"><span data-stu-id="1226b-149">classification</span></span> | <span data-ttu-id="1226b-150">Перечисление</span><span class="sxs-lookup"><span data-stu-id="1226b-150">Enum</span></span> | <span data-ttu-id="1226b-151">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="1226b-151">Specification of the incident.</span></span> <span data-ttu-id="1226b-152">Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="1226b-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="1226b-153">решение</span><span class="sxs-lookup"><span data-stu-id="1226b-153">determination</span></span> | <span data-ttu-id="1226b-154">Перечисление</span><span class="sxs-lookup"><span data-stu-id="1226b-154">Enum</span></span> | <span data-ttu-id="1226b-155">Указывает на определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="1226b-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="1226b-156">Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="1226b-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="1226b-157">tags</span><span class="sxs-lookup"><span data-stu-id="1226b-157">tags</span></span> | <span data-ttu-id="1226b-158">Список строк</span><span class="sxs-lookup"><span data-stu-id="1226b-158">string List</span></span> | <span data-ttu-id="1226b-159">Список тегов инцидента.</span><span class="sxs-lookup"><span data-stu-id="1226b-159">List of Incident tags.</span></span>
<span data-ttu-id="1226b-160">alerts</span><span class="sxs-lookup"><span data-stu-id="1226b-160">alerts</span></span> | <span data-ttu-id="1226b-161">Список оповещений</span><span class="sxs-lookup"><span data-stu-id="1226b-161">Alert List</span></span> | <span data-ttu-id="1226b-162">Список связанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="1226b-162">List of related alerts.</span></span> <span data-ttu-id="1226b-163">В этой статье приведены примеры документации по API [происшествий](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="1226b-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>
