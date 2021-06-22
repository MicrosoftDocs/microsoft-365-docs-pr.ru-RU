---
title: Обзор обнаружения устройств
description: Узнайте, как использовать обнаружение конечных точек в Microsoft 365 Defender, чтобы найти неугодные устройства в сети
keywords: обнаружение, обнаружение, пассивная, проактивность, сеть, видимость, сервер, рабочие станции, бортовых, неустановимых устройств
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
ms.openlocfilehash: 16baaa6fd9865140d42c0ca3a566427f761a28c2
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062217"
---
# <a name="device-discovery-overview"></a><span data-ttu-id="92bfa-104">Обзор обнаружения устройств</span><span class="sxs-lookup"><span data-stu-id="92bfa-104">Device discovery overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="92bfa-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="92bfa-105">**Applies to:**</span></span>
- [<span data-ttu-id="92bfa-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="92bfa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="92bfa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="92bfa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="92bfa-108">Защита среды требует инвентаризации устройств, которые находятся в вашей сети.</span><span class="sxs-lookup"><span data-stu-id="92bfa-108">Protecting your environment requires taking inventory of the devices that are in your network.</span></span> <span data-ttu-id="92bfa-109">Однако устройства сопоставления в сети часто могут быть дорогостоящими, сложными и трудоемкими.</span><span class="sxs-lookup"><span data-stu-id="92bfa-109">However, mapping devices in a network can often be expensive, challenging, and time-consuming.</span></span> 

<span data-ttu-id="92bfa-110">Microsoft Defender для конечной точки предоставляет возможности обнаружения устройств, которые помогают находить неустановленные устройства, подключенные к корпоративной сети без необходимости дополнительных устройств или громоздких изменений процесса.</span><span class="sxs-lookup"><span data-stu-id="92bfa-110">Microsoft Defender for Endpoint provides a device discovery capability that helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span>


<span data-ttu-id="92bfa-111">Возможность обнаружения устройства позволяет:</span><span class="sxs-lookup"><span data-stu-id="92bfa-111">The device discovery capability allows you to:</span></span>

- <span data-ttu-id="92bfa-112">**Обнаружение конечных точек предприятия, подключенных к корпоративной сети**</span><span class="sxs-lookup"><span data-stu-id="92bfa-112">**Discover enterprise endpoints connected to your corporate network**</span></span> <br>
<span data-ttu-id="92bfa-113">Используя базовые или стандартные параметры обнаружения, вы можете обнаружить рабочие станции, серверы и мобильные конечные точки, которые еще не доступны в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="92bfa-113">Using either basic or standard discovery options, you can discover workstations, servers, and mobile endpoints that are not yet onboarded to Microsoft Defender for Endpoint.</span></span>  

- <span data-ttu-id="92bfa-114">**Обнаруженные конечные точки на борту**</span><span class="sxs-lookup"><span data-stu-id="92bfa-114">**Onboard discovered endpoints**</span></span><br>
<span data-ttu-id="92bfa-115">Неугомонные конечные точки в сети вводят в сеть уязвимости и риски.</span><span class="sxs-lookup"><span data-stu-id="92bfa-115">Unmanaged endpoints in your network introduce vulnerabilities and risks to your network.</span></span> <span data-ttu-id="92bfa-116">Их в службу может повысить видимость безопасности на них.</span><span class="sxs-lookup"><span data-stu-id="92bfa-116">Onboarding them to the service can increase the security visibility on them.</span></span> 

<span data-ttu-id="92bfa-117">В сочетании с этой возможностью будет доступна новая рекомендация по безопасности для бортовых устройств в Microsoft Defender для конечной точки в рамках существующего опыта управления угрозами и уязвимостью.</span><span class="sxs-lookup"><span data-stu-id="92bfa-117">In conjunction with this capability, a new security recommendation to onboard devices to Microsoft Defender for Endpoint will be available as part of the existing Threat and Vulnerability Management experience.</span></span>



## <a name="discovery-methods"></a><span data-ttu-id="92bfa-118">Методы обнаружения</span><span class="sxs-lookup"><span data-stu-id="92bfa-118">Discovery methods</span></span>
<span data-ttu-id="92bfa-119">Существует два способа обнаружения:</span><span class="sxs-lookup"><span data-stu-id="92bfa-119">There are two modes of discovery:</span></span> 

-   <span data-ttu-id="92bfa-120">Базовое открытие</span><span class="sxs-lookup"><span data-stu-id="92bfa-120">Basic discovery</span></span> 
-   <span data-ttu-id="92bfa-121">Стандартные открытия (рекомендуемые)</span><span class="sxs-lookup"><span data-stu-id="92bfa-121">Standard discovery (recommended)</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="92bfa-122">Обнаружение установлено в базовом режиме.</span><span class="sxs-lookup"><span data-stu-id="92bfa-122">Discovery is set to basic mode.</span></span> <span data-ttu-id="92bfa-123">Эту конфигурацию можно сохранить на странице параметры.</span><span class="sxs-lookup"><span data-stu-id="92bfa-123">You can choose to retain this configuration through the settings page.</span></span> <span data-ttu-id="92bfa-124">Стандартным открытием будет режим по умолчанию для всех клиентов, начиная с 19 июля 2021 г., если они не будут изменены на странице параметров до этой даты.</span><span class="sxs-lookup"><span data-stu-id="92bfa-124">Standard discovery will be the default mode for all customers starting July 19, 2021 - unless modified through the settings page before this date.</span></span>

### <a name="basic-discovery"></a><span data-ttu-id="92bfa-125">Базовое открытие</span><span class="sxs-lookup"><span data-stu-id="92bfa-125">Basic discovery</span></span> 

<span data-ttu-id="92bfa-126">В этом режиме конечные точки будут пассивно собирать события в сети и извлекать из них сведения об устройствах.</span><span class="sxs-lookup"><span data-stu-id="92bfa-126">In this mode, endpoints will passively collect events in your network and extract device information from them.</span></span> <span data-ttu-id="92bfa-127">Базовое открытие использует двоичный SenseNDR.exe для пассивного сбора сетевых данных, и сетевой трафик не будет инициирован.</span><span class="sxs-lookup"><span data-stu-id="92bfa-127">Basic discovery uses the SenseNDR.exe binary for passive network data collection and no network traffic will be initiated.</span></span> <span data-ttu-id="92bfa-128">Конечные точки просто извлекают данные из каждого сетевого трафика, который рассматривается на бортовом устройстве.</span><span class="sxs-lookup"><span data-stu-id="92bfa-128">Endpoints will simply extract data from every network traffic that is seen by an onboarded device.</span></span> 

### <a name="standard-discovery"></a><span data-ttu-id="92bfa-129">Стандартные открытия</span><span class="sxs-lookup"><span data-stu-id="92bfa-129">Standard discovery</span></span> 

<span data-ttu-id="92bfa-130">Этот режим позволяет конечным точкам активно зондировать наблюдаемые устройства в сети для обогащения собранных данных, помогая создать надежный и согласованный инвентарь устройств.</span><span class="sxs-lookup"><span data-stu-id="92bfa-130">This mode allows endpoints to actively probe observed devices in the network to enrich collected data - helping you build a reliable and coherent device inventory.</span></span> <span data-ttu-id="92bfa-131">Стандартный режим использует смарт-активные прорабывки, чтобы обнаружить еще больше сведений о наблюдаемых устройствах для обогащения существующей информации об устройстве.</span><span class="sxs-lookup"><span data-stu-id="92bfa-131">Standard mode uses smart, active probing to discover even more information about observed devices to enrich existing device information.</span></span>  

<span data-ttu-id="92bfa-132">Когда включен стандартный режим, минимальная и ничтожная сетевая активность, созданная датчиком обнаружения, может наблюдаться средствами сетевого мониторинга в организации.</span><span class="sxs-lookup"><span data-stu-id="92bfa-132">When Standard mode is enabled, minimal and negligible network activity generated by the discovery sensor might be observed by network monitoring tools in your organization.</span></span>  

 <span data-ttu-id="92bfa-133">Если вы решите не включить этот режим, вы получите ограниченную видимость неугодных конечных точек в сети.</span><span class="sxs-lookup"><span data-stu-id="92bfa-133">If you choose not to enable this mode, you will only gain limited visibility of unmanaged endpoints in your network.</span></span>

<span data-ttu-id="92bfa-134">Стандартные открытия используют различные скрипты PowerShell для активного зондировать устройства в сети.</span><span class="sxs-lookup"><span data-stu-id="92bfa-134">Standard discovery uses various PowerShell scripts to actively probe devices in the network.</span></span> <span data-ttu-id="92bfa-135">Эти скрипты PowerShell подписаны Корпорацией Майкрософт и выполняются из следующего расположения: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` .</span><span class="sxs-lookup"><span data-stu-id="92bfa-135">Those PowerShell scripts are Microsoft signed and are executed from the following location: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`.</span></span> <span data-ttu-id="92bfa-136">Например, `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.</span><span class="sxs-lookup"><span data-stu-id="92bfa-136">For example, `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.</span></span>

<span data-ttu-id="92bfa-137">Вы можете изменить и настроить параметры обнаружения, дополнительные сведения см. в [статью Configure device discovery.](configure-device-discovery.md)</span><span class="sxs-lookup"><span data-stu-id="92bfa-137">You can change and customize your discovery settings, for more information see [Configure device discovery](configure-device-discovery.md).</span></span>

> [!NOTE]
> <span data-ttu-id="92bfa-138">Механизм обнаружения различает сетевые события, полученные в корпоративной сети, и вне корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="92bfa-138">The discovery engine distinguishes between network events that are received in the corporate network versus outside of the corporate network.</span></span> <span data-ttu-id="92bfa-139">Устройства, не подключенные к корпоративным сетям, не будут обнаружены или указаны в инвентаризации устройств.</span><span class="sxs-lookup"><span data-stu-id="92bfa-139">Devices that are not connected to corporate networks will not be discovered or listed in the device inventory.</span></span> 



## <a name="device-inventory"></a><span data-ttu-id="92bfa-140">Инвентаризация устройств</span><span class="sxs-lookup"><span data-stu-id="92bfa-140">Device Inventory</span></span> 
<span data-ttu-id="92bfa-141">Устройства, обнаруженные, но еще не включенные и защищенные Microsoft Defender для конечной точки, будут перечислены в инвентаре устройств в вкладке Конечные точки. Теперь можно использовать новый фильтр в списке инвентаризации устройств, который называется состоянием onboarding, который может иметь любое из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="92bfa-141">Devices that have been discovered but have not yet been onboarded and secured by Microsoft Defender for Endpoint will be listed in Device Inventory within the Endpoints tab. You can now use a new filter in the device inventory list called Onboarding status which can have any of the following values:</span></span>

- <span data-ttu-id="92bfa-142">Onboarded — конечная точка находится на борту в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="92bfa-142">Onboarded – The endpoint is onboarded to Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="92bfa-143">Можно установить на борт — конечная точка была обнаружена в сети, а операционная система была определена как та, которая поддерживается Microsoft Defender для конечной точки, но в настоящее время не установлена на борт.</span><span class="sxs-lookup"><span data-stu-id="92bfa-143">Can be onboarded – The endpoint was discovered in the network and the Operating System was identified as one that is supported by Microsoft Defender for Endpoint, but it is not currently onboarded.</span></span> <span data-ttu-id="92bfa-144">Мы настоятельно рекомендуем использовать эти устройства.</span><span class="sxs-lookup"><span data-stu-id="92bfa-144">We highly recommend onboarding these devices.</span></span>
- <span data-ttu-id="92bfa-145">Неподдермеченная — конечная точка была обнаружена в сети, но не поддерживается Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="92bfa-145">Unsupported – The endpoint was discovered in the network but is not supported by Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="92bfa-146">Недостаточная информация — система не могла определить надежность устройства.</span><span class="sxs-lookup"><span data-stu-id="92bfa-146">Insufficient info – The system could not determine the supportability of the device.</span></span> <span data-ttu-id="92bfa-147">Включение стандартных открытий на других устройствах в сети может обогатить обнаруженные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="92bfa-147">Enabling standard discovery on more devices in the network can enrich the discovered attributes.</span></span> 
 

![Изображение панели мониторинга инвентаризации устройств](images/2b62255cd3a9dd42f3219e437b956fb9.png)

> [!TIP]
> <span data-ttu-id="92bfa-149">Вы всегда можете применить фильтры, чтобы исключить неугодные устройства из списка инвентаризации устройств.</span><span class="sxs-lookup"><span data-stu-id="92bfa-149">You can always apply filters to exclude unmanaged devices from the device inventory list.</span></span> <span data-ttu-id="92bfa-150">Вы также можете использовать столбец состояния в запросах API для фильтрации неугодных устройств.</span><span class="sxs-lookup"><span data-stu-id="92bfa-150">You can also use the onboarding status column on API queries to filter out unmanaged devices.</span></span> 

## <a name="vulnerability-assessment-on-discovered-devices"></a><span data-ttu-id="92bfa-151">Оценка уязвимости на обнаруженных устройствах</span><span class="sxs-lookup"><span data-stu-id="92bfa-151">Vulnerability assessment on discovered devices</span></span>
<span data-ttu-id="92bfa-152">Уязвимости и риски на ваших устройствах, а также других обнаруженных неукомпонантных устройствах в сети являются частью текущих потоков TVM в рамках "Security Рекомендации" и представлены на страницах сущности на портале.</span><span class="sxs-lookup"><span data-stu-id="92bfa-152">Vulnerabilities and risks on your devices as well as other discovered unmanaged devices in the network are part of the current TVM flows under "Security Recommendations" and represented in entity pages across the portal.</span></span> <span data-ttu-id="92bfa-153">Поиск связанных с "SSH" рекомендаций по безопасности для поиска уязвимостей SSH, связанных с неустановляемой и управляемой устройствами.</span><span class="sxs-lookup"><span data-stu-id="92bfa-153">Search for "SSH" related security recommendations to find SSH vulnerabilities that are related for unmanaged and managed devices.</span></span> 

![Изображение панели мониторинга рекомендаций по безопасности](images/1156c82ffadd356ce329d1cf551e806c.png)  

## <a name="use-advanced-hunting-on-discovered-devices"></a><span data-ttu-id="92bfa-155">Использование расширенных средств охоты на обнаруженных устройствах</span><span class="sxs-lookup"><span data-stu-id="92bfa-155">Use Advanced Hunting on discovered devices</span></span>
<span data-ttu-id="92bfa-156">Запросы Advanced Hunting можно использовать для получения видимости на обнаруженных устройствах.</span><span class="sxs-lookup"><span data-stu-id="92bfa-156">You can use Advanced Hunting queries to gain visibility on discovered devices.</span></span>
<span data-ttu-id="92bfa-157">Сведения об обнаруженных конечных точках в таблице DeviceInfo или сетевые сведения об этих устройствах в таблице DeviceNetworkInfo.</span><span class="sxs-lookup"><span data-stu-id="92bfa-157">Find details about discovered Endpoints in the DeviceInfo table, or network-related information about those devices in the DeviceNetworkInfo table.</span></span>
  

![Изображение передовой охоты](images/f48ba1779eddee9872f167453c24e5c9.png)


<span data-ttu-id="92bfa-159">Обнаружение устройств использует Microsoft Defender для бортовых устройств конечной точки в качестве источника сетевых данных для атрибутики действий с неконтборантными устройствами.</span><span class="sxs-lookup"><span data-stu-id="92bfa-159">Device discovery leverages Microsoft Defender for Endpoint onboarded devices as a network data source to attribute activities to non-onboarded devices.</span></span> <span data-ttu-id="92bfa-160">Это означает, что если на бортовом устройстве Microsoft Defender для конечной точки передается не включающееся устройство, действия на устройстве, не включаемом, можно увидеть на временной шкале и в таблице Advanced hunting DeviceNetworkEvents.</span><span class="sxs-lookup"><span data-stu-id="92bfa-160">This means that if a Microsoft Defender for Endpoint onboarded device communicated with a non-onboarded device, activities on the non-onboarded device can be seen on the timeline and through the Advanced hunting DeviceNetworkEvents table.</span></span> 



<span data-ttu-id="92bfa-161">Новые события основаны на подключениях протокола управления передачей (TCP) и соответствуют текущей схеме DeviceNetworkEvents.</span><span class="sxs-lookup"><span data-stu-id="92bfa-161">New events are Transmission Control Protocol (TCP) connections-based and will fit to the current DeviceNetworkEvents scheme.</span></span> <span data-ttu-id="92bfa-162">TCP включит устройство с включенной поддержкой Защитника Майкрософт для конечной точки с включенной не microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="92bfa-162">TCP ingress to the Microsoft Defender for Endpoint enabled device from a non-Microsoft Defender for Endpoint enabled.</span></span>  

<span data-ttu-id="92bfa-163">Добавлены следующие типы действий:</span><span class="sxs-lookup"><span data-stu-id="92bfa-163">The following action types have also been added:</span></span>  

- <span data-ttu-id="92bfa-164">ConnectionAttempt — попытка установить подключение TCP (syn)</span><span class="sxs-lookup"><span data-stu-id="92bfa-164">ConnectionAttempt - An attempt to establish a TCP connection (syn)</span></span>  
- <span data-ttu-id="92bfa-165">ConnectionAcknowledged — подтверждение того, что подключение TCP было принято (syn\ack)</span><span class="sxs-lookup"><span data-stu-id="92bfa-165">ConnectionAcknowledged - An acknowledgment that a TCP connection was accepted (syn\ack)</span></span>  

<span data-ttu-id="92bfa-166">Вы можете попробовать этот пример запроса:</span><span class="sxs-lookup"><span data-stu-id="92bfa-166">You can try this example query:</span></span>  

```
DeviceNetworkEvents  
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"  
| take 10  
```


## <a name="changed-behavior"></a><span data-ttu-id="92bfa-167">Изменено поведение</span><span class="sxs-lookup"><span data-stu-id="92bfa-167">Changed behavior</span></span>
<span data-ttu-id="92bfa-168">В следующем разделе перечислены изменения, которые будут наблюдаться в Центре безопасности Microsoft Defender для конечной точки и/или Microsoft 365, когда эта возможность включена.</span><span class="sxs-lookup"><span data-stu-id="92bfa-168">The following section lists the changes you'll observe in Microsoft Defender for Endpoint and/or Microsoft 365 Security Center when this capability is enabled.</span></span> 
 
1.  <span data-ttu-id="92bfa-169">Предполагается, что устройства, не встраив в Microsoft Defender до конечной точки, будут отображаться в инвентаризации устройств, расширенных запросах на охоту и API.</span><span class="sxs-lookup"><span data-stu-id="92bfa-169">Devices that are not onboarded to Microsoft Defender to Endpoint are expected to appear in the device inventory, advanced hunting, and API queries.</span></span> <span data-ttu-id="92bfa-170">Это может значительно увеличить размер результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="92bfa-170">This may significantly increase the size of query results.</span></span> 
    1. <span data-ttu-id="92bfa-171">Таблицы DeviceInfo и DeviceNetworkInfo в Advanced Hunting теперь будут удерживать обнаруженное устройство.</span><span class="sxs-lookup"><span data-stu-id="92bfa-171">"DeviceInfo" and "DeviceNetworkInfo" tables in Advanced Hunting will now hold discovered device.</span></span> <span data-ttu-id="92bfa-172">Эти устройства можно отфильтровать с помощью атрибута OnboardingStatus.</span><span class="sxs-lookup"><span data-stu-id="92bfa-172">You can filter out those devices by using “OnboardingStatus” attribute.</span></span>

    2. <span data-ttu-id="92bfa-173">Ожидается, что обнаруженные устройства будут отображаться в результатах запроса API потокового воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="92bfa-173">Discovered devices are expected to appear in Streaming API query results.</span></span> <span data-ttu-id="92bfa-174">Эти устройства можно отфильтровать с помощью `OnboardingStatus` фильтра в запросе.</span><span class="sxs-lookup"><span data-stu-id="92bfa-174">You can filter out those devices by using the `OnboardingStatus` filter in your query.</span></span> 

2.  <span data-ttu-id="92bfa-175">Неугомные устройства будут назначены существующим группам устройств на основе определенных критериев.</span><span class="sxs-lookup"><span data-stu-id="92bfa-175">Unmanaged devices will be assigned to existing device groups based on the defined criteria.</span></span> 
3.  <span data-ttu-id="92bfa-176">В редких случаях обнаружение standard может вызывать оповещения на сетевых мониторах или средствах безопасности.</span><span class="sxs-lookup"><span data-stu-id="92bfa-176">In rare cases, Standard discovery might trigger alerts on network monitors or security tools.</span></span> <span data-ttu-id="92bfa-177">Чтобы предотвратить повторение этих проблем, пожалуйста, предосообщите о таких событиях.</span><span class="sxs-lookup"><span data-stu-id="92bfa-177">Please provide feedback, if you experience such events, to help prevent these issues from recurring.</span></span> <span data-ttu-id="92bfa-178">Вы можете явно исключить конкретные цели или целые подсети от активного зондироваться стандартным обнаружением.</span><span class="sxs-lookup"><span data-stu-id="92bfa-178">You can explicitly exclude specific targets or entire subnets from being actively probed by Standard discovery.</span></span> 



## <a name="next-steps"></a><span data-ttu-id="92bfa-179">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="92bfa-179">Next steps</span></span>
- [<span data-ttu-id="92bfa-180">Настройка обнаружения устройств</span><span class="sxs-lookup"><span data-stu-id="92bfa-180">Configure device discovery</span></span>](configure-device-discovery.md)
- [<span data-ttu-id="92bfa-181">FaQs обнаружения устройств</span><span class="sxs-lookup"><span data-stu-id="92bfa-181">Device discovery FAQs</span></span>](device-discovery-faq.md)
