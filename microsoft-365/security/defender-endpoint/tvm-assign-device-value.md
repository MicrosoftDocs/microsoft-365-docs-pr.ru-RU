---
title: Назначение значения устройства — управления угрозами и уязвимостью
description: Узнайте, как назначить устройству низкое, нормальное или высокое значение, чтобы помочь вам различать приоритеты активов.
keywords: Microsoft defender atp device value, threat and vulnerability management device value, high value devices, device value exposure score
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
ms.openlocfilehash: 3cecee8b80f179f67cb48f62e1d9238a51825bfd
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500205"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a><span data-ttu-id="1b107-104">Назначение значения устройства — управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="1b107-104">Assign device value - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1b107-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1b107-105">**Applies to:**</span></span>

- [<span data-ttu-id="1b107-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1b107-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="1b107-107">Управление угрозами и уязвимостями</span><span class="sxs-lookup"><span data-stu-id="1b107-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="1b107-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b107-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1b107-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1b107-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1b107-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1b107-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1b107-111">Определение значения устройства позволяет различать приоритеты активов.</span><span class="sxs-lookup"><span data-stu-id="1b107-111">Defining a device’s value helps you differentiate between asset priorities.</span></span> <span data-ttu-id="1b107-112">Значение устройства используется для включения аппетита к риску отдельного актива в расчет оценки воздействия на угрозы и уязвимости управления рисками.</span><span class="sxs-lookup"><span data-stu-id="1b107-112">The device value is used to incorporate the risk appetite of an individual asset into the threat and vulnerability management exposure score calculation.</span></span> <span data-ttu-id="1b107-113">Устройства, назначенные как "высокое значение", будут получать больше веса.</span><span class="sxs-lookup"><span data-stu-id="1b107-113">Devices assigned as “high value” will receive more weight.</span></span>

<span data-ttu-id="1b107-114">Вы также можете использовать API значения [за установленного устройства.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="1b107-114">You can also use the [set device value API](set-device-value.md).</span></span>

<span data-ttu-id="1b107-115">Параметры значения устройства:</span><span class="sxs-lookup"><span data-stu-id="1b107-115">Device value options:</span></span>

- <span data-ttu-id="1b107-116">Низкие</span><span class="sxs-lookup"><span data-stu-id="1b107-116">Low</span></span>
- <span data-ttu-id="1b107-117">С обычными интервалами (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1b107-117">Normal (Default)</span></span>
- <span data-ttu-id="1b107-118">Высокие</span><span class="sxs-lookup"><span data-stu-id="1b107-118">High</span></span>

<span data-ttu-id="1b107-119">Примеры устройств, которые должны быть назначены с высоким значением:</span><span class="sxs-lookup"><span data-stu-id="1b107-119">Examples of devices that should be assigned a high value:</span></span>

- <span data-ttu-id="1b107-120">Контроллеры домена, Active Directory</span><span class="sxs-lookup"><span data-stu-id="1b107-120">Domain controllers, Active Directory</span></span>
- <span data-ttu-id="1b107-121">Устройства с подключением к Интернету</span><span class="sxs-lookup"><span data-stu-id="1b107-121">Internet facing devices</span></span>
- <span data-ttu-id="1b107-122">VIP-устройства</span><span class="sxs-lookup"><span data-stu-id="1b107-122">VIP devices</span></span>
- <span data-ttu-id="1b107-123">Устройства, на которые размещены внутренние и внешние производственные службы</span><span class="sxs-lookup"><span data-stu-id="1b107-123">Devices hosting internal/external production services</span></span>

## <a name="choose-device-value"></a><span data-ttu-id="1b107-124">Выбор значения устройства</span><span class="sxs-lookup"><span data-stu-id="1b107-124">Choose device value</span></span>

1. <span data-ttu-id="1b107-125">Перейдите на любую страницу устройства, самое простое место из инвентаризации устройства.</span><span class="sxs-lookup"><span data-stu-id="1b107-125">Navigate to any device page, the easiest place is from the device inventory.</span></span>

2. <span data-ttu-id="1b107-126">Выберите **значение Device** из трех точек рядом со стойкой действий в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="1b107-126">Select **Device value** from three dots next to the actions bar at the top of the page.</span></span>

    ![Пример отсев значения устройства.](images/tvm-device-value-dropdown.png)

3. <span data-ttu-id="1b107-128">Вылет появится с текущим значением устройства и его значением.</span><span class="sxs-lookup"><span data-stu-id="1b107-128">A flyout will appear with the current device value and what it means.</span></span> <span data-ttu-id="1b107-129">Просмотрите значение устройства и выберите устройство, которое лучше всего подходит вашему устройству.</span><span class="sxs-lookup"><span data-stu-id="1b107-129">Review the value of the device and choose the one that best fits your device.</span></span>
<span data-ttu-id="1b107-130">![Пример вылета значения устройства.](images/tvm-device-value-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="1b107-130">![Example of the device value flyout.](images/tvm-device-value-flyout.png)</span></span>

## <a name="how-device-value-impacts-your-exposure-score"></a><span data-ttu-id="1b107-131">Влияние значения устройства на оценку экспозиции</span><span class="sxs-lookup"><span data-stu-id="1b107-131">How device value impacts your exposure score</span></span>

<span data-ttu-id="1b107-132">Оценка экспозиции — это средневзвешение для всех устройств.</span><span class="sxs-lookup"><span data-stu-id="1b107-132">The exposure score is a weighted average across all devices.</span></span> <span data-ttu-id="1b107-133">Если у вас есть группы устройств, вы также можете фильтровать оценку по группе устройств.</span><span class="sxs-lookup"><span data-stu-id="1b107-133">If you have device groups, you can also filter the score by device group.</span></span>

- <span data-ttu-id="1b107-134">Вес обычных устройств составляет 1</span><span class="sxs-lookup"><span data-stu-id="1b107-134">Normal devices have a weight of 1</span></span>
- <span data-ttu-id="1b107-135">Устройства с низким значением имеют вес 0,75</span><span class="sxs-lookup"><span data-stu-id="1b107-135">Low value devices have a weight of 0.75</span></span>
- <span data-ttu-id="1b107-136">Устройства с высоким значением имеют вес NumberOfAssets / 10.</span><span class="sxs-lookup"><span data-stu-id="1b107-136">High value devices have a weight of NumberOfAssets / 10.</span></span>
    - <span data-ttu-id="1b107-137">Если у вас 100 устройств, каждое устройство с высоким значением будет иметь вес 10 (100/10)</span><span class="sxs-lookup"><span data-stu-id="1b107-137">If you have 100 devices, each high value device will have a weight of 10 (100/10)</span></span>

## <a name="related-topics"></a><span data-ttu-id="1b107-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1b107-138">Related topics</span></span>

- [<span data-ttu-id="1b107-139">Обзор управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="1b107-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="1b107-140">Оценка экспозиции</span><span class="sxs-lookup"><span data-stu-id="1b107-140">Exposure Score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="1b107-141">Интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="1b107-141">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)