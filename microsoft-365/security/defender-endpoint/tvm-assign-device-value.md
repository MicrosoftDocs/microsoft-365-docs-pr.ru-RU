---
title: Назначение значения устройства — контроль угроз и уязвимостей
description: Узнайте, как назначить устройству низкое, нормальное или высокое значение, чтобы помочь вам различать приоритеты активов.
keywords: Значение Microsoft Defender для конечных устройств, контроль угроз и уязвимостей устройства, устройства с высоким значением, оценка экспозиции значения устройства
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ca6c88b08b331eb65035387a9c070d0914b1651d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935201"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a><span data-ttu-id="5785a-104">Назначение значения устройства — контроль угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="5785a-104">Assign device value - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5785a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5785a-105">**Applies to:**</span></span>

- [<span data-ttu-id="5785a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5785a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5785a-107">Угроза и управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="5785a-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="5785a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5785a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5785a-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5785a-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5785a-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="5785a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="5785a-111">Определение значения устройства позволяет различать приоритеты активов.</span><span class="sxs-lookup"><span data-stu-id="5785a-111">Defining a device’s value helps you differentiate between asset priorities.</span></span> <span data-ttu-id="5785a-112">Значение устройства используется для включения аппетита к риску отдельного актива в контроль угроз и уязвимостей оценки экспозиции.</span><span class="sxs-lookup"><span data-stu-id="5785a-112">The device value is used to incorporate the risk appetite of an individual asset into the threat and vulnerability management exposure score calculation.</span></span> <span data-ttu-id="5785a-113">Устройства, назначенные как "высокое значение", будут получать больше веса.</span><span class="sxs-lookup"><span data-stu-id="5785a-113">Devices assigned as “high value” will receive more weight.</span></span>

<span data-ttu-id="5785a-114">Вы также можете использовать API значения [за установленного устройства.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="5785a-114">You can also use the [set device value API](set-device-value.md).</span></span>

<span data-ttu-id="5785a-115">Параметры значения устройства:</span><span class="sxs-lookup"><span data-stu-id="5785a-115">Device value options:</span></span>

- <span data-ttu-id="5785a-116">Низкие</span><span class="sxs-lookup"><span data-stu-id="5785a-116">Low</span></span>
- <span data-ttu-id="5785a-117">С обычными интервалами (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5785a-117">Normal (Default)</span></span>
- <span data-ttu-id="5785a-118">Фишинговое сообщение с</span><span class="sxs-lookup"><span data-stu-id="5785a-118">High</span></span>

<span data-ttu-id="5785a-119">Примеры устройств, которые должны быть назначены с высоким значением:</span><span class="sxs-lookup"><span data-stu-id="5785a-119">Examples of devices that should be assigned a high value:</span></span>

- <span data-ttu-id="5785a-120">Контроллеры домена, Active Directory</span><span class="sxs-lookup"><span data-stu-id="5785a-120">Domain controllers, Active Directory</span></span>
- <span data-ttu-id="5785a-121">Устройства с подключением к Интернету</span><span class="sxs-lookup"><span data-stu-id="5785a-121">Internet facing devices</span></span>
- <span data-ttu-id="5785a-122">VIP-устройства</span><span class="sxs-lookup"><span data-stu-id="5785a-122">VIP devices</span></span>
- <span data-ttu-id="5785a-123">Устройства, на которые размещены внутренние и внешние производственные службы</span><span class="sxs-lookup"><span data-stu-id="5785a-123">Devices hosting internal/external production services</span></span>

## <a name="choose-device-value"></a><span data-ttu-id="5785a-124">Выбор значения устройства</span><span class="sxs-lookup"><span data-stu-id="5785a-124">Choose device value</span></span>

1. <span data-ttu-id="5785a-125">Перейдите на любую страницу устройства, самое простое место из инвентаризации устройства.</span><span class="sxs-lookup"><span data-stu-id="5785a-125">Navigate to any device page, the easiest place is from the device inventory.</span></span>

2. <span data-ttu-id="5785a-126">Выберите **значение Device** из трех точек рядом со стойкой действий в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="5785a-126">Select **Device value** from three dots next to the actions bar at the top of the page.</span></span>

    ![Пример отсев значения устройства.](images/tvm-device-value-dropdown.png)

3. <span data-ttu-id="5785a-128">Вылет появится с текущим значением устройства и его значением.</span><span class="sxs-lookup"><span data-stu-id="5785a-128">A flyout will appear with the current device value and what it means.</span></span> <span data-ttu-id="5785a-129">Просмотрите значение устройства и выберите устройство, которое лучше всего подходит вашему устройству.</span><span class="sxs-lookup"><span data-stu-id="5785a-129">Review the value of the device and choose the one that best fits your device.</span></span>
<span data-ttu-id="5785a-130">![Пример вылета значения устройства.](images/tvm-device-value-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="5785a-130">![Example of the device value flyout.](images/tvm-device-value-flyout.png)</span></span>

## <a name="how-device-value-impacts-your-exposure-score"></a><span data-ttu-id="5785a-131">Влияние значения устройства на оценку экспозиции</span><span class="sxs-lookup"><span data-stu-id="5785a-131">How device value impacts your exposure score</span></span>

<span data-ttu-id="5785a-132">Оценка экспозиции — это средневзвешение для всех устройств.</span><span class="sxs-lookup"><span data-stu-id="5785a-132">The exposure score is a weighted average across all devices.</span></span> <span data-ttu-id="5785a-133">Если у вас есть группы устройств, вы также можете фильтровать оценку по группе устройств.</span><span class="sxs-lookup"><span data-stu-id="5785a-133">If you have device groups, you can also filter the score by device group.</span></span>

- <span data-ttu-id="5785a-134">Вес обычных устройств составляет 1</span><span class="sxs-lookup"><span data-stu-id="5785a-134">Normal devices have a weight of 1</span></span>
- <span data-ttu-id="5785a-135">Устройства с низким значением имеют вес 0,75</span><span class="sxs-lookup"><span data-stu-id="5785a-135">Low value devices have a weight of 0.75</span></span>
- <span data-ttu-id="5785a-136">Устройства с высоким значением имеют вес NumberOfAssets / 10.</span><span class="sxs-lookup"><span data-stu-id="5785a-136">High value devices have a weight of NumberOfAssets / 10.</span></span>
    - <span data-ttu-id="5785a-137">Если у вас 100 устройств, каждое устройство с высоким значением будет иметь вес 10 (100/10)</span><span class="sxs-lookup"><span data-stu-id="5785a-137">If you have 100 devices, each high value device will have a weight of 10 (100/10)</span></span>

## <a name="related-topics"></a><span data-ttu-id="5785a-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5785a-138">Related topics</span></span>

- [<span data-ttu-id="5785a-139">Обзор угроз и управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="5785a-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="5785a-140">Оценка экспозиции</span><span class="sxs-lookup"><span data-stu-id="5785a-140">Exposure Score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="5785a-141">Интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="5785a-141">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)