---
title: Тип ресурса исследования
description: Объект Microsoft Defender для исследования конечных точек.
keywords: apis, graph api, supported apis, get, alerts, investigations
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 252b273995d48d523604802c0c4365a613d86dbe
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771733"
---
# <a name="investigation-resource-type"></a><span data-ttu-id="a4dff-104">Тип ресурса исследования</span><span class="sxs-lookup"><span data-stu-id="a4dff-104">Investigation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a4dff-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a4dff-105">**Applies to:**</span></span>
- [<span data-ttu-id="a4dff-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a4dff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a4dff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4dff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a4dff-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a4dff-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a4dff-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="a4dff-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="a4dff-110">Представляете объект автоматического расследования в Защитнике для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a4dff-110">Represent an Automated Investigation entity in Defender for Endpoint.</span></span>
<br> <span data-ttu-id="a4dff-111">Дополнительные [сведения см.](automated-investigations.md) в обзоре автоматизированных расследований.</span><span class="sxs-lookup"><span data-stu-id="a4dff-111">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>

## <a name="methods"></a><span data-ttu-id="a4dff-112">Методы</span><span class="sxs-lookup"><span data-stu-id="a4dff-112">Methods</span></span>
<span data-ttu-id="a4dff-113">Метод</span><span class="sxs-lookup"><span data-stu-id="a4dff-113">Method</span></span>|<span data-ttu-id="a4dff-114">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="a4dff-114">Return Type</span></span> |<span data-ttu-id="a4dff-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a4dff-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="a4dff-116">Исследования списка</span><span class="sxs-lookup"><span data-stu-id="a4dff-116">List Investigations</span></span>](get-investigation-collection.md) | <span data-ttu-id="a4dff-117">Коллекция исследований</span><span class="sxs-lookup"><span data-stu-id="a4dff-117">Investigation collection</span></span> | <span data-ttu-id="a4dff-118">Get collection of Investigation</span><span class="sxs-lookup"><span data-stu-id="a4dff-118">Get collection of Investigation</span></span>
[<span data-ttu-id="a4dff-119">Получить одно исследование</span><span class="sxs-lookup"><span data-stu-id="a4dff-119">Get single Investigation</span></span>](get-investigation-object.md) | <span data-ttu-id="a4dff-120">Объект исследования</span><span class="sxs-lookup"><span data-stu-id="a4dff-120">Investigation entity</span></span> | <span data-ttu-id="a4dff-121">Получает одно целое исследование.</span><span class="sxs-lookup"><span data-stu-id="a4dff-121">Gets single Investigation entity.</span></span>
[<span data-ttu-id="a4dff-122">Начать исследование</span><span class="sxs-lookup"><span data-stu-id="a4dff-122">Start Investigation</span></span>](initiate-autoir-investigation.md) | <span data-ttu-id="a4dff-123">Объект исследования</span><span class="sxs-lookup"><span data-stu-id="a4dff-123">Investigation entity</span></span> | <span data-ttu-id="a4dff-124">Запускает исследование на устройстве.</span><span class="sxs-lookup"><span data-stu-id="a4dff-124">Starts Investigation on a device.</span></span>


## <a name="properties"></a><span data-ttu-id="a4dff-125">Свойства</span><span class="sxs-lookup"><span data-stu-id="a4dff-125">Properties</span></span>
<span data-ttu-id="a4dff-126">Свойство</span><span class="sxs-lookup"><span data-stu-id="a4dff-126">Property</span></span> |  <span data-ttu-id="a4dff-127">Тип</span><span class="sxs-lookup"><span data-stu-id="a4dff-127">Type</span></span>    |   <span data-ttu-id="a4dff-128">Описание</span><span class="sxs-lookup"><span data-stu-id="a4dff-128">Description</span></span>
:---|:---|:---
<span data-ttu-id="a4dff-129">id</span><span class="sxs-lookup"><span data-stu-id="a4dff-129">id</span></span> | <span data-ttu-id="a4dff-130">String</span><span class="sxs-lookup"><span data-stu-id="a4dff-130">String</span></span> | <span data-ttu-id="a4dff-131">Удостоверение объекта расследования.</span><span class="sxs-lookup"><span data-stu-id="a4dff-131">Identity of the investigation entity.</span></span> 
<span data-ttu-id="a4dff-132">startTime</span><span class="sxs-lookup"><span data-stu-id="a4dff-132">startTime</span></span> | <span data-ttu-id="a4dff-133">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="a4dff-133">DateTime Nullable</span></span> | <span data-ttu-id="a4dff-134">Дата и время создания расследования.</span><span class="sxs-lookup"><span data-stu-id="a4dff-134">The date and time when the investigation was created.</span></span> 
<span data-ttu-id="a4dff-135">endTime</span><span class="sxs-lookup"><span data-stu-id="a4dff-135">endTime</span></span> | <span data-ttu-id="a4dff-136">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="a4dff-136">DateTime Nullable</span></span> | <span data-ttu-id="a4dff-137">Дата и время завершения расследования.</span><span class="sxs-lookup"><span data-stu-id="a4dff-137">The date and time when the investigation was completed.</span></span> 
<span data-ttu-id="a4dff-138">cancelledBy</span><span class="sxs-lookup"><span data-stu-id="a4dff-138">cancelledBy</span></span> | <span data-ttu-id="a4dff-139">String</span><span class="sxs-lookup"><span data-stu-id="a4dff-139">String</span></span> | <span data-ttu-id="a4dff-140">ID пользователя или приложения, отменив это расследование.</span><span class="sxs-lookup"><span data-stu-id="a4dff-140">The ID of the user/application that canceled that investigation.</span></span> 
<span data-ttu-id="a4dff-141">investigationState</span><span class="sxs-lookup"><span data-stu-id="a4dff-141">investigationState</span></span> | <span data-ttu-id="a4dff-142">Перечисление</span><span class="sxs-lookup"><span data-stu-id="a4dff-142">Enum</span></span> | <span data-ttu-id="a4dff-143">Текущее состояние расследования.</span><span class="sxs-lookup"><span data-stu-id="a4dff-143">The current state of the investigation.</span></span> <span data-ttu-id="a4dff-144">Возможные значения: "Unknown", "Terminated", "SuccessfullyRemediated", 'Benign', 'Failed', 'PartiallyRemediated', "Running", "PendingApproval", "PendingResource", "PartiallyInvestigated", "TerminatedByUser", "TerminatedBySystem", "Queued", "InnerFailure", "PreexistingAlert", "UnsupportedAlert", "SuppressedAlert".</span><span class="sxs-lookup"><span data-stu-id="a4dff-144">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="a4dff-145">statusDetails</span><span class="sxs-lookup"><span data-stu-id="a4dff-145">statusDetails</span></span> | <span data-ttu-id="a4dff-146">String</span><span class="sxs-lookup"><span data-stu-id="a4dff-146">String</span></span> | <span data-ttu-id="a4dff-147">Дополнительные сведения о состоянии расследования.</span><span class="sxs-lookup"><span data-stu-id="a4dff-147">Additional information about the state of the investigation.</span></span>
<span data-ttu-id="a4dff-148">machineId</span><span class="sxs-lookup"><span data-stu-id="a4dff-148">machineId</span></span> | <span data-ttu-id="a4dff-149">String</span><span class="sxs-lookup"><span data-stu-id="a4dff-149">String</span></span> | <span data-ttu-id="a4dff-150">ID устройства, на котором выполняется расследование.</span><span class="sxs-lookup"><span data-stu-id="a4dff-150">The ID of the device on which the investigation is executed.</span></span>
<span data-ttu-id="a4dff-151">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="a4dff-151">computerDnsName</span></span> | <span data-ttu-id="a4dff-152">String</span><span class="sxs-lookup"><span data-stu-id="a4dff-152">String</span></span> | <span data-ttu-id="a4dff-153">Имя устройства, на котором выполняется расследование.</span><span class="sxs-lookup"><span data-stu-id="a4dff-153">The name of the device on which the investigation is executed.</span></span>
<span data-ttu-id="a4dff-154">triggeringAlertId</span><span class="sxs-lookup"><span data-stu-id="a4dff-154">triggeringAlertId</span></span> | <span data-ttu-id="a4dff-155">String</span><span class="sxs-lookup"><span data-stu-id="a4dff-155">String</span></span> | <span data-ttu-id="a4dff-156">ID оповещений, которые вызвали расследование.</span><span class="sxs-lookup"><span data-stu-id="a4dff-156">The ID of the alert that triggered the investigation.</span></span>


## <a name="json-representation"></a><span data-ttu-id="a4dff-157">Представление Json</span><span class="sxs-lookup"><span data-stu-id="a4dff-157">Json representation</span></span>

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
