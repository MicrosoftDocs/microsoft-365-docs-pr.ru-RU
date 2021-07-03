---
title: Настройка обнаружения устройств
description: Узнайте, как настроить обнаружение устройств в Microsoft 365 Defender с помощью базового или стандартного обнаружения
keywords: базовый, стандартный, настройка обнаружения конечной точки, обнаружения устройств
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ee56ed2949ea72771d8f08570d4352dbe7548d52
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286949"
---
# <a name="configure-device-discovery"></a><span data-ttu-id="6f94e-104">Настройка обнаружения устройств</span><span class="sxs-lookup"><span data-stu-id="6f94e-104">Configure device discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6f94e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6f94e-105">**Applies to:**</span></span>
- [<span data-ttu-id="6f94e-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6f94e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="6f94e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f94e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6f94e-108">Обнаружение можно настроить в стандартном или базовом режиме.</span><span class="sxs-lookup"><span data-stu-id="6f94e-108">Discovery can be configured to be on standard or basic mode.</span></span> <span data-ttu-id="6f94e-109">Используйте стандартный параметр, чтобы активно находить устройства в сети, что лучше гарантирует обнаружение конечных точек и обеспечивает более богатую классификацию устройств.</span><span class="sxs-lookup"><span data-stu-id="6f94e-109">Use the standard option to actively find devices in your network, which will better guarantee the discovery of endpoints and provide richer device classification.</span></span> 

<span data-ttu-id="6f94e-110">Вы можете настроить список устройств, используемых для выполнения стандартных открытий.</span><span class="sxs-lookup"><span data-stu-id="6f94e-110">You can customize the list of devices that are used to perform standard discovery.</span></span> <span data-ttu-id="6f94e-111">Вы можете включить стандартные открытия на всех бортовых устройствах, которые также поддерживают эту возможность (в настоящее время — только Windows 10 устройства) или выбрать подмножество или подмножество устройств, указав теги устройств.</span><span class="sxs-lookup"><span data-stu-id="6f94e-111">You can either enable standard discovery on all the onboarded devices that also support this capability (currently - Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f94e-112">Для предварительного просмотра сначала необходимо включить функции Preview в Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="6f94e-112">For preview, you'll first need to turn on the Preview features in Microsoft Defender Security Center.</span></span>
> <span data-ttu-id="6f94e-113">Затем вы можете получить доступ к конфигурации обнаружения устройства в Microsoft 365 центре безопасности.</span><span class="sxs-lookup"><span data-stu-id="6f94e-113">You can then access the device discovery configuration in Microsoft 365 security center.</span></span> <span data-ttu-id="6f94e-114">Список неугодных устройств и рекомендаций по безопасности будет доступен в центре безопасности Центр безопасности в Microsoft Defender и Microsoft 365, а плитки панели мониторинга будут доступны только в Microsoft 365 центре безопасности.</span><span class="sxs-lookup"><span data-stu-id="6f94e-114">The list of unmanaged devices and security recommendations will be available in both Microsoft Defender Security Center and Microsoft 365 security center, while the dashboard tiles will only be available in Microsoft 365 security center.</span></span>

<span data-ttu-id="6f94e-115">Следуйте следующим шагам по настройке в центре Microsoft 365 безопасности:</span><span class="sxs-lookup"><span data-stu-id="6f94e-115">Take the following configuration steps in Microsoft 365 security center:</span></span>

1. <span data-ttu-id="6f94e-116">Перейдите **к Параметры > устройств.**</span><span class="sxs-lookup"><span data-stu-id="6f94e-116">Navigate to **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="6f94e-117">Выберите режим обнаружения, который можно использовать на бортовых устройствах.</span><span class="sxs-lookup"><span data-stu-id="6f94e-117">Select the discovery mode to use on your onboarded devices.</span></span>
3. <span data-ttu-id="6f94e-118">Если вы выбрали для использования стандартные открытия, выберите устройства, которые можно использовать для активного прорабтки: все устройства или подмножество, указав теги устройств.</span><span class="sxs-lookup"><span data-stu-id="6f94e-118">If you've selected to use standard discovery, select which devices to use for active probing: all devices or on a subset by specifying their device tags.</span></span>
4. <span data-ttu-id="6f94e-119">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6f94e-119">Click **Save**.</span></span>

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a><span data-ttu-id="6f94e-120">Исключить активное зондировать устройства при стандартных обнаружениях</span><span class="sxs-lookup"><span data-stu-id="6f94e-120">Exclude devices from being actively probed in standard discovery</span></span>

<span data-ttu-id="6f94e-121">Если в сети есть устройства, которые не следует активно сканировать (например, устройства, используемые в качестве соты для другого средства безопасности), можно также определить список исключений, чтобы запретить их отсканировать.</span><span class="sxs-lookup"><span data-stu-id="6f94e-121">If there are devices on your network which should not be actively scanned (for example, devices used as honeypots for another security tool), you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="6f94e-122">Обратите внимание, что устройства по-прежнему можно обнаружить с помощью основного режима обнаружения.</span><span class="sxs-lookup"><span data-stu-id="6f94e-122">Note that devices can still be discovered using Basic discovery mode.</span></span> <span data-ttu-id="6f94e-123">Эти устройства будут пассивно обнаружены, но не будут активно зондироваться.</span><span class="sxs-lookup"><span data-stu-id="6f94e-123">Those devices will be passively discovered but won't be actively probed.</span></span> 

## <a name="select-networks-to-monitor"></a><span data-ttu-id="6f94e-124">Выбор сетей для мониторинга</span><span class="sxs-lookup"><span data-stu-id="6f94e-124">Select networks to monitor</span></span>

 <span data-ttu-id="6f94e-125">Microsoft Defender для конечной точки анализирует сеть и определяет, является ли она корпоративной сетью, которую необходимо контролировать, или не корпоративной сетью, которую можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="6f94e-125">Microsoft Defender for Endpoint analyzes a network and determines if it is a corporate network that needs to be monitored or a non-corporate network that can be ignored.</span></span> <span data-ttu-id="6f94e-126">Корпоративные сети обычно выбираются для мониторинга.</span><span class="sxs-lookup"><span data-stu-id="6f94e-126">Corporate networks are typically chosen to be monitored.</span></span> <span data-ttu-id="6f94e-127">Однако вы можете переопредить это решение, выбрав мониторинг не корпоративных сетей, в которых находятся бортовых устройств.</span><span class="sxs-lookup"><span data-stu-id="6f94e-127">However, you can override this decision by choosing to monitor non-corporate networks where onboarded devices are found.</span></span> 

<span data-ttu-id="6f94e-128">Вы можете настроить место обнаружения устройства, указав, какие сети следует отслеживать.</span><span class="sxs-lookup"><span data-stu-id="6f94e-128">You can configure where device discovery can be performed by specifying which networks to monitor.</span></span> <span data-ttu-id="6f94e-129">При мониторинге сети на ней может быть выполнено обнаружение устройства.</span><span class="sxs-lookup"><span data-stu-id="6f94e-129">When a network is monitored, device discovery can be performed on it.</span></span> 

<span data-ttu-id="6f94e-130">Список сетей, в которых можно выполнить обнаружение устройств, отображается на странице **Monitored networks.**</span><span class="sxs-lookup"><span data-stu-id="6f94e-130">A list of networks where device discovery can be performed is shown in the **Monitored networks** page.</span></span> 

> [!NOTE]
> <span data-ttu-id="6f94e-131">Только топ-50 сетей (в зависимости от количества связанных устройств) будут доступны в списке сети.</span><span class="sxs-lookup"><span data-stu-id="6f94e-131">Only top 50 networks (according to the number of associated devices) will be available in the network list.</span></span> 

<span data-ttu-id="6f94e-132">Список отслеживаемой сети сортируются в зависимости от общего числа устройств, замеченных в сети за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="6f94e-132">The list of monitored networks is sorted based upon the total number of devices seen on the network in the last 7 days.</span></span>

<span data-ttu-id="6f94e-133">Вы можете применить фильтр для просмотра любого из следующих состояниях обнаружения сети:</span><span class="sxs-lookup"><span data-stu-id="6f94e-133">You can apply a filter to view any of the following network discovery states:</span></span>

- <span data-ttu-id="6f94e-134">**Отслеживаемая сеть** — сети, в которых выполняется обнаружение устройств.</span><span class="sxs-lookup"><span data-stu-id="6f94e-134">**Monitored networks** - Networks where device discovery is performed.</span></span>
- <span data-ttu-id="6f94e-135">**Игнорируются сети** . Эта сеть будет игнорироваться и обнаружение устройства не будет выполнено на ней.</span><span class="sxs-lookup"><span data-stu-id="6f94e-135">**Ignored networks** - This network will be ignored and device discovery will not be performed on it.</span></span>
- <span data-ttu-id="6f94e-136">**Все** — будут отображаться как отслеживаются, так и игнорируются сети.</span><span class="sxs-lookup"><span data-stu-id="6f94e-136">**All** - Both monitored and ignored networks will be displayed.</span></span>

### <a name="configure-the-network-monitor-state"></a><span data-ttu-id="6f94e-137">Настройка состояния сетевого монитора</span><span class="sxs-lookup"><span data-stu-id="6f94e-137">Configure the network monitor state</span></span>

<span data-ttu-id="6f94e-138">Вы контролируете, где происходит обнаружение устройства.</span><span class="sxs-lookup"><span data-stu-id="6f94e-138">You control where device discovery takes place.</span></span> <span data-ttu-id="6f94e-139">Отслеживаемая сеть — это место, в котором будет выполняться обнаружение устройств, которые обычно являются корпоративными сетями.</span><span class="sxs-lookup"><span data-stu-id="6f94e-139">Monitored networks is where device discovery will be performed and are typically corporate networks.</span></span> <span data-ttu-id="6f94e-140">Вы также можете игнорировать сети или выбрать начальную классификацию обнаружения после изменения состояния.</span><span class="sxs-lookup"><span data-stu-id="6f94e-140">You can also choose to ignore networks or select the initial discovery classification after modifying a state.</span></span>

<span data-ttu-id="6f94e-141">Выбор начальной классификации обнаружения означает применение состояния сетевого монитора, выполненного по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6f94e-141">Choosing the initial discovery classification means applying the default system-made network monitor state.</span></span> <span data-ttu-id="6f94e-142">Выбор состояния сетевого мониторинга по умолчанию означает, что сети, которые были определены как корпоративные, будут отслеживаться, а те, которые определены как некорпоративные, будут игнорироваться автоматически.</span><span class="sxs-lookup"><span data-stu-id="6f94e-142">Selecting the default system-made network monitor state means that networks that were identified to be corporate, will be monitored, and ones identified as non-corporate, will be ignored automatically.</span></span>

1. <span data-ttu-id="6f94e-143">Выберите **Параметры > устройства**.</span><span class="sxs-lookup"><span data-stu-id="6f94e-143">Select **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="6f94e-144">Выберите **отслеживаемую сеть.**</span><span class="sxs-lookup"><span data-stu-id="6f94e-144">Select **Monitored networks**.</span></span>
3. <span data-ttu-id="6f94e-145">Просмотр списка сетей.</span><span class="sxs-lookup"><span data-stu-id="6f94e-145">View the list of networks.</span></span>
4. <span data-ttu-id="6f94e-146">Выберите три точки рядом с сетевым именем.</span><span class="sxs-lookup"><span data-stu-id="6f94e-146">Select the three dots next to the network name.</span></span>
5. <span data-ttu-id="6f94e-147">Выберите, хотите ли вы отслеживать, игнорировать или использовать начальную классификацию обнаружения.</span><span class="sxs-lookup"><span data-stu-id="6f94e-147">Choose whether you want to monitor, ignore, or use the initial discovery classification.</span></span>

    > [!WARNING]
    >
    > - <span data-ttu-id="6f94e-148">Выбор мониторинга сети, которая не была идентифицирована Microsoft Defender для endpoint как корпоративная сеть, может привести к обнаружению устройств вне корпоративной сети и, следовательно, обнаружить домашние или другие не корпоративные устройства.</span><span class="sxs-lookup"><span data-stu-id="6f94e-148">Choosing to monitor a network that was not identified by Microsoft Defender for Endpoint as a corporate network can cause device discovery outside of your corporate network, and may therefore detect home or other non-corporate devices.</span></span>
    > - <span data-ttu-id="6f94e-149">Решение игнорировать сеть остановит мониторинг и обнаружение устройств в этой сети.</span><span class="sxs-lookup"><span data-stu-id="6f94e-149">Choosing to ignore a network will stop monitoring and discovering devices in that network.</span></span> <span data-ttu-id="6f94e-150">Устройства, которые уже были обнаружены, не будут удалены из инвентаризации, но не будут обновляться, а сведения будут храниться до истечения срока хранения данных в Защитнике для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="6f94e-150">Devices that were already discovered will not be removed from the inventory, but will no longer be updated, and details will be retained until the data retention period of the Defender for Endpoint expires.</span></span>
    > - <span data-ttu-id="6f94e-151">Прежде чем выбирать для мониторинга не корпоративных сетей, необходимо убедиться, что у вас есть разрешение на это.</span><span class="sxs-lookup"><span data-stu-id="6f94e-151">Before choosing to monitor non-corporate networks, you must ensure you have permission to do so.</span></span>

6. <span data-ttu-id="6f94e-152">Убедитесь, что вы хотите внести изменения.</span><span class="sxs-lookup"><span data-stu-id="6f94e-152">Confirm that you want to make the change.</span></span> 

## <a name="explore-devices-in-the-network"></a><span data-ttu-id="6f94e-153">Изучение устройств в сети</span><span class="sxs-lookup"><span data-stu-id="6f94e-153">Explore devices in the network</span></span>

<span data-ttu-id="6f94e-154">Вы можете использовать следующий расширенный запрос для охоты, чтобы получить дополнительный контекст для каждого имени сети, описанного в списке сетей.</span><span class="sxs-lookup"><span data-stu-id="6f94e-154">You can use the following advanced hunting query to get more context about each network name described in the networks list.</span></span> <span data-ttu-id="6f94e-155">В запросе перечислены все подключенные устройства, подключенные к определенной сети в течение последних 7 дней.</span><span class="sxs-lookup"><span data-stu-id="6f94e-155">The query lists all the onboarded devices that were connected to a certain network within the last 7 days.</span></span>

```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| summarize arg_max(Timestamp, *) by DeviceId
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"
```

## <a name="see-also"></a><span data-ttu-id="6f94e-156">См. также</span><span class="sxs-lookup"><span data-stu-id="6f94e-156">See also</span></span>

- [<span data-ttu-id="6f94e-157">Обзор обнаружения устройств</span><span class="sxs-lookup"><span data-stu-id="6f94e-157">Device discovery overview</span></span>](device-discovery.md)
- [<span data-ttu-id="6f94e-158">FaQs обнаружения устройств</span><span class="sxs-lookup"><span data-stu-id="6f94e-158">Device discovery FAQs</span></span>](device-discovery-faq.md)
