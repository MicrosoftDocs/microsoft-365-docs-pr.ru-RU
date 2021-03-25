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
ms.technology: mde
ms.openlocfilehash: 9bfec2c4e65a390189556c14347eaf17236fb95e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187304"
---
# <a name="software-resource-type"></a><span data-ttu-id="b4d35-104">Тип ресурсов программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b4d35-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b4d35-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b4d35-105">**Applies to:**</span></span>
- [<span data-ttu-id="b4d35-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b4d35-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b4d35-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4d35-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b4d35-108">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b4d35-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b4d35-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b4d35-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b4d35-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b4d35-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="b4d35-111">Методы</span><span class="sxs-lookup"><span data-stu-id="b4d35-111">Methods</span></span>

<span data-ttu-id="b4d35-112">Метод</span><span class="sxs-lookup"><span data-stu-id="b4d35-112">Method</span></span> |<span data-ttu-id="b4d35-113">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="b4d35-113">Return Type</span></span> |<span data-ttu-id="b4d35-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b4d35-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="b4d35-115">Список программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b4d35-115">List software</span></span>](get-software.md) | <span data-ttu-id="b4d35-116">Коллекция программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b4d35-116">Software collection</span></span> | <span data-ttu-id="b4d35-117">Список инвентаризации программного обеспечения организации.</span><span class="sxs-lookup"><span data-stu-id="b4d35-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="b4d35-118">Получить программное обеспечение по ID</span><span class="sxs-lookup"><span data-stu-id="b4d35-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="b4d35-119">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="b4d35-119">Software</span></span> | <span data-ttu-id="b4d35-120">Получите определенное программное обеспечение по его программному ИД.</span><span class="sxs-lookup"><span data-stu-id="b4d35-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="b4d35-121">Список распространения версий программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b4d35-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="b4d35-122">Коллекция рассылки</span><span class="sxs-lookup"><span data-stu-id="b4d35-122">Distribution collection</span></span> | <span data-ttu-id="b4d35-123">Список распространения программных версий по ID программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="b4d35-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="b4d35-124">Список машин по программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="b4d35-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="b4d35-125">Коллекция MachineRef</span><span class="sxs-lookup"><span data-stu-id="b4d35-125">MachineRef collection</span></span> | <span data-ttu-id="b4d35-126">Извлечение списка устройств, связанных с программным ИД.</span><span class="sxs-lookup"><span data-stu-id="b4d35-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="b4d35-127">Список уязвимостей по программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="b4d35-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="b4d35-128">[Коллекция уязвимостей](vulnerability.md)</span><span class="sxs-lookup"><span data-stu-id="b4d35-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="b4d35-129">Извлечение списка уязвимостей, связанных с программным ИД.</span><span class="sxs-lookup"><span data-stu-id="b4d35-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="b4d35-130">Отсутствие КБ</span><span class="sxs-lookup"><span data-stu-id="b4d35-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="b4d35-131">Коллекция KB</span><span class="sxs-lookup"><span data-stu-id="b4d35-131">KB collection</span></span> | <span data-ttu-id="b4d35-132">Получить список отсутствующих KBs, связанных с ID программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b4d35-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="b4d35-133">Свойства</span><span class="sxs-lookup"><span data-stu-id="b4d35-133">Properties</span></span>

<span data-ttu-id="b4d35-134">Свойство</span><span class="sxs-lookup"><span data-stu-id="b4d35-134">Property</span></span> |   <span data-ttu-id="b4d35-135">Тип</span><span class="sxs-lookup"><span data-stu-id="b4d35-135">Type</span></span>   |   <span data-ttu-id="b4d35-136">Описание</span><span class="sxs-lookup"><span data-stu-id="b4d35-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="b4d35-137">id</span><span class="sxs-lookup"><span data-stu-id="b4d35-137">id</span></span> | <span data-ttu-id="b4d35-138">Строка</span><span class="sxs-lookup"><span data-stu-id="b4d35-138">String</span></span> | <span data-ttu-id="b4d35-139">ID программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b4d35-139">Software ID</span></span>
<span data-ttu-id="b4d35-140">Имя</span><span class="sxs-lookup"><span data-stu-id="b4d35-140">Name</span></span> | <span data-ttu-id="b4d35-141">Строка</span><span class="sxs-lookup"><span data-stu-id="b4d35-141">String</span></span> | <span data-ttu-id="b4d35-142">Имя программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b4d35-142">Software name</span></span>
<span data-ttu-id="b4d35-143">Поставщик</span><span class="sxs-lookup"><span data-stu-id="b4d35-143">Vendor</span></span> | <span data-ttu-id="b4d35-144">Строка</span><span class="sxs-lookup"><span data-stu-id="b4d35-144">String</span></span> | <span data-ttu-id="b4d35-145">Имя поставщика программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b4d35-145">Software vendor name</span></span>
<span data-ttu-id="b4d35-146">Недостатки</span><span class="sxs-lookup"><span data-stu-id="b4d35-146">Weaknesses</span></span> | <span data-ttu-id="b4d35-147">Длинное целое</span><span class="sxs-lookup"><span data-stu-id="b4d35-147">Long</span></span> | <span data-ttu-id="b4d35-148">Количество обнаруженных уязвимостей</span><span class="sxs-lookup"><span data-stu-id="b4d35-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="b4d35-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="b4d35-149">publicExploit</span></span> | <span data-ttu-id="b4d35-150">Boolean</span><span class="sxs-lookup"><span data-stu-id="b4d35-150">Boolean</span></span> | <span data-ttu-id="b4d35-151">Существует публичный эксплойт для некоторых уязвимостей</span><span class="sxs-lookup"><span data-stu-id="b4d35-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="b4d35-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="b4d35-152">activeAlert</span></span> | <span data-ttu-id="b4d35-153">Boolean</span><span class="sxs-lookup"><span data-stu-id="b4d35-153">Boolean</span></span> | <span data-ttu-id="b4d35-154">Активное оповещение связано с этим программным обеспечением</span><span class="sxs-lookup"><span data-stu-id="b4d35-154">Active alert is associated with this software</span></span>
<span data-ttu-id="b4d35-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="b4d35-155">exposedMachines</span></span> | <span data-ttu-id="b4d35-156">Длинное целое</span><span class="sxs-lookup"><span data-stu-id="b4d35-156">Long</span></span> | <span data-ttu-id="b4d35-157">Количество открытых устройств</span><span class="sxs-lookup"><span data-stu-id="b4d35-157">Number of exposed devices</span></span>
<span data-ttu-id="b4d35-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="b4d35-158">impactScore</span></span> | <span data-ttu-id="b4d35-159">Двойное с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="b4d35-159">Double</span></span> | <span data-ttu-id="b4d35-160">Влияние оценки экспозиции этого программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b4d35-160">Exposure score impact of this software</span></span>
