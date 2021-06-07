---
title: Методы и свойства программного обеспечения
description: Извлекает последние оповещений.
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 14291cbbba2272d268a8e79b6df7bd87992885db
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771417"
---
# <a name="software-resource-type"></a><span data-ttu-id="b2aa0-104">Тип ресурсов программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b2aa0-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b2aa0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b2aa0-105">**Applies to:**</span></span>
- [<span data-ttu-id="b2aa0-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b2aa0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b2aa0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2aa0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b2aa0-108">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b2aa0-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b2aa0-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b2aa0-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b2aa0-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b2aa0-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="b2aa0-111">Методы</span><span class="sxs-lookup"><span data-stu-id="b2aa0-111">Methods</span></span>

<span data-ttu-id="b2aa0-112">Метод</span><span class="sxs-lookup"><span data-stu-id="b2aa0-112">Method</span></span> |<span data-ttu-id="b2aa0-113">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="b2aa0-113">Return Type</span></span> |<span data-ttu-id="b2aa0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b2aa0-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="b2aa0-115">Список программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b2aa0-115">List software</span></span>](get-software.md) | <span data-ttu-id="b2aa0-116">Коллекция программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b2aa0-116">Software collection</span></span> | <span data-ttu-id="b2aa0-117">Список инвентаризации программного обеспечения организации.</span><span class="sxs-lookup"><span data-stu-id="b2aa0-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="b2aa0-118">Получить программное обеспечение по ИД</span><span class="sxs-lookup"><span data-stu-id="b2aa0-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="b2aa0-119">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="b2aa0-119">Software</span></span> | <span data-ttu-id="b2aa0-120">Получите определенное программное обеспечение по его программному ИД.</span><span class="sxs-lookup"><span data-stu-id="b2aa0-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="b2aa0-121">Список распространения версий программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b2aa0-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="b2aa0-122">Коллекция рассылки</span><span class="sxs-lookup"><span data-stu-id="b2aa0-122">Distribution collection</span></span> | <span data-ttu-id="b2aa0-123">Список распространения программных версий по ID программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="b2aa0-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="b2aa0-124">Список компьютеров по программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="b2aa0-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="b2aa0-125">Коллекция MachineRef</span><span class="sxs-lookup"><span data-stu-id="b2aa0-125">MachineRef collection</span></span> | <span data-ttu-id="b2aa0-126">Извлечение списка устройств, связанных с программным ИД.</span><span class="sxs-lookup"><span data-stu-id="b2aa0-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="b2aa0-127">Список уязвимостей по программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="b2aa0-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="b2aa0-128">[Коллекция уязвимостей](vulnerability.md)</span><span class="sxs-lookup"><span data-stu-id="b2aa0-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="b2aa0-129">Извлечение списка уязвимостей, связанных с программным ИД.</span><span class="sxs-lookup"><span data-stu-id="b2aa0-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="b2aa0-130">Получить недостающие КБ</span><span class="sxs-lookup"><span data-stu-id="b2aa0-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="b2aa0-131">Коллекция KB</span><span class="sxs-lookup"><span data-stu-id="b2aa0-131">KB collection</span></span> | <span data-ttu-id="b2aa0-132">Получить список отсутствующих KBs, связанных с ID программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b2aa0-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="b2aa0-133">Свойства</span><span class="sxs-lookup"><span data-stu-id="b2aa0-133">Properties</span></span>

<span data-ttu-id="b2aa0-134">Свойство</span><span class="sxs-lookup"><span data-stu-id="b2aa0-134">Property</span></span> |   <span data-ttu-id="b2aa0-135">Тип</span><span class="sxs-lookup"><span data-stu-id="b2aa0-135">Type</span></span>   |   <span data-ttu-id="b2aa0-136">Описание</span><span class="sxs-lookup"><span data-stu-id="b2aa0-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="b2aa0-137">id</span><span class="sxs-lookup"><span data-stu-id="b2aa0-137">id</span></span> | <span data-ttu-id="b2aa0-138">String</span><span class="sxs-lookup"><span data-stu-id="b2aa0-138">String</span></span> | <span data-ttu-id="b2aa0-139">ID программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b2aa0-139">Software ID</span></span>
<span data-ttu-id="b2aa0-140">Имя</span><span class="sxs-lookup"><span data-stu-id="b2aa0-140">Name</span></span> | <span data-ttu-id="b2aa0-141">String</span><span class="sxs-lookup"><span data-stu-id="b2aa0-141">String</span></span> | <span data-ttu-id="b2aa0-142">Имя программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b2aa0-142">Software name</span></span>
<span data-ttu-id="b2aa0-143">Поставщик</span><span class="sxs-lookup"><span data-stu-id="b2aa0-143">Vendor</span></span> | <span data-ttu-id="b2aa0-144">String</span><span class="sxs-lookup"><span data-stu-id="b2aa0-144">String</span></span> | <span data-ttu-id="b2aa0-145">Имя поставщика программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b2aa0-145">Software vendor name</span></span>
<span data-ttu-id="b2aa0-146">Недостатки</span><span class="sxs-lookup"><span data-stu-id="b2aa0-146">Weaknesses</span></span> | <span data-ttu-id="b2aa0-147">Длинное целое</span><span class="sxs-lookup"><span data-stu-id="b2aa0-147">Long</span></span> | <span data-ttu-id="b2aa0-148">Количество обнаруженных уязвимостей</span><span class="sxs-lookup"><span data-stu-id="b2aa0-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="b2aa0-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="b2aa0-149">publicExploit</span></span> | <span data-ttu-id="b2aa0-150">Логический</span><span class="sxs-lookup"><span data-stu-id="b2aa0-150">Boolean</span></span> | <span data-ttu-id="b2aa0-151">Существует публичный эксплойт для некоторых уязвимостей</span><span class="sxs-lookup"><span data-stu-id="b2aa0-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="b2aa0-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="b2aa0-152">activeAlert</span></span> | <span data-ttu-id="b2aa0-153">Логический</span><span class="sxs-lookup"><span data-stu-id="b2aa0-153">Boolean</span></span> | <span data-ttu-id="b2aa0-154">Активное оповещение связано с этим программным обеспечением</span><span class="sxs-lookup"><span data-stu-id="b2aa0-154">Active alert is associated with this software</span></span>
<span data-ttu-id="b2aa0-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="b2aa0-155">exposedMachines</span></span> | <span data-ttu-id="b2aa0-156">Длинное целое</span><span class="sxs-lookup"><span data-stu-id="b2aa0-156">Long</span></span> | <span data-ttu-id="b2aa0-157">Количество открытых устройств</span><span class="sxs-lookup"><span data-stu-id="b2aa0-157">Number of exposed devices</span></span>
<span data-ttu-id="b2aa0-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="b2aa0-158">impactScore</span></span> | <span data-ttu-id="b2aa0-159">Двойное с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="b2aa0-159">Double</span></span> | <span data-ttu-id="b2aa0-160">Влияние оценки экспозиции этого программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b2aa0-160">Exposure score impact of this software</span></span>
